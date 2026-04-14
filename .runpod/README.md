# Qwen 2.5 Coder 7B vLLM Worker

Deploy `Qwen/Qwen2.5-Coder-7B-Instruct` on RunPod Hub with an OpenAI-compatible `vLLM` worker tuned for affordable code generation and coding assistants.

## Best for

- editor or CLI copilots that need a coding-tuned model,
- repo helpers and code-completion endpoints on 24 GB GPUs,
- users searching for `Qwen Coder`, `coding assistant`, or `vLLM` on RunPod Hub.

## Request shapes

- `prompt` for `/v1/completions`
- `messages` for `/v1/chat/completions`
- `route` + `body` for explicit OpenAI-compatible requests

## Main knobs

- `MODEL_NAME`
- `MAX_MODEL_LEN`
- `GPU_MEMORY_UTILIZATION`
- `MAX_NUM_SEQS`
- `DEFAULT_MAX_TOKENS`
- `MAX_CONCURRENCY`

The default deployment model is `Qwen/Qwen2.5-Coder-7B-Instruct`, while the smoke test uses a smaller coder-family model to keep validation faster and cheaper.
