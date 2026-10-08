# Local LLM coding assistant

This repository is documentation-first, so a coding assistant can help revise
curriculum, references, and project briefs without adding an inference
dependency to the repository. Keep the model runtime and downloaded weights
outside the repository; use Git to review every proposed change.

## A setup that can grow with your hardware

Use a coding client separately from the model server. This lets the same client
work with a small model on your computer now and a faster local or remote
OpenAI-compatible server later.

- **Model server:** `llama.cpp`'s `llama-server` can run GGUF models on CPU and
  provides an OpenAI-compatible API. Start with CPU inference for broad
  compatibility; use supported acceleration only when the host has it.
- **Coding client:** Aider is a terminal-based option that can connect to an
  OpenAI-compatible endpoint and uses the current Git checkout as its work
  area.
- **Model:** choose an instruction-tuned coding model in GGUF format. Check its
  license and the model publisher's download instructions. A quantized
  `Q4_K_M` model is a practical starting point when memory is limited.

### Choose a starting size

Available memory, not just the model's advertised parameter count, determines
what will work. The operating system, model weights, context/KV cache, and
coding client all need memory.

| Host memory | Starting point | Notes |
| --- | --- | --- |
| 8 GB or less, including many 2014 Mac minis | 1B–3B parameters, Q4 quantization, 2K–4K context | Prefer CPU mode, close memory-heavy apps, and expect slow generation. |
| 16 GB | Try a 3B–7B Q4 model, starting with 4K context | If the system swaps or slows sharply, use a smaller model or context. |
| More memory and a capable GPU | Increase model size or context gradually | Check runtime/model compatibility and monitor memory use. |

A 2014 Mac mini is an older Intel machine, so treat it as a low-memory,
CPU-first host, not as a machine for large models. Confirm its installed RAM
and macOS version before choosing a runtime; use the runtime's current
installation instructions for that operating system. An unspecified laptop
may be a better inference host, especially if it has more memory or supported
GPU acceleration.

## First local connection

Install `llama.cpp` using its current official instructions, then start the
server with a downloaded GGUF model. Keep the listener on loopback:

```sh
llama-server \
  --model /path/to/model.gguf \
  --ctx-size 4096 \
  --n-gpu-layers 0 \
  --host 127.0.0.1 \
  --port 8080
```

The model file path is a placeholder. Adjust context size to available memory;
use GPU layers only if the host and build support them. The server's model
identifier may depend on the runtime version and launch options.

In a second terminal, install Aider using its current official instructions and
point it at the local OpenAI-compatible endpoint. Replace
`<served-model-name>` with the identifier exposed by the server:

```sh
OPENAI_API_BASE=http://127.0.0.1:8080/v1 \
OPENAI_API_KEY=local \
aider --model openai/<served-model-name>
```

Check Aider's current documentation if its environment variable names or
endpoint configuration have changed. Start with a small documentation edit,
then inspect `git diff` before accepting anything. Small local models may not
follow complex coding instructions reliably; keep tasks narrow and verify
claims, links, and edits yourself.

## Scale without changing the repository

1. **One computer:** run both server and coding client locally. Store model
   weights outside this checkout.
2. **Another computer you control:** move inference to a stronger laptop or
   workstation and point the same client at its OpenAI-compatible endpoint.
   Do not bind an unauthenticated server to a public or untrusted network.
   For remote access, use an authenticated, encrypted route such as a trusted
   VPN or SSH tunnel, and follow the server's security guidance.
3. **Hosted inference:** use a compatible hosted endpoint if local hardware
   becomes a bottleneck. Review the provider's data-retention and privacy terms
   first; prompts may contain repository contents.

Keep endpoint settings in your shell or a local, untracked configuration file;
do not commit API keys, model weights, private prompts, or machine-specific
paths. Before committing assistant-generated changes, review the full diff and
run any relevant checks. This repository currently has no code test or build
commands to run for documentation edits.
