# Qwen 2.5 Coder 7B Worker For RunPod Hub

This repo packages an OpenAI-compatible `vLLM` worker around `Qwen/Qwen2.5-Coder-7B-Instruct` for lower-cost 24 GB GPU deployments on RunPod Serverless.

It is meant for practical coding use cases:

- code assistant backends,
- lightweight repo copilots,
- CLI and editor integrations that want a coding-tuned model without H100 pricing.

## Positioning

This listing is the affordable coding lane in the portfolio:

- 24 GB GPU deployment targets,
- coder-tuned Qwen defaults instead of generic chat defaults,
- OpenAI-style request shapes that fit existing code-assistant clients quickly.

The handler still forwards plain completions, chat completions, and explicit OpenAI-style routes through the local `vLLM` server inside the worker container.

## Presets

The Hub metadata ships with presets tuned for affordable coding use:

- `Starter Coder 1.5B`
- `Cheap Coder 7B`
- `Long Context Coder 7B`

The default model is:

- `Qwen/Qwen2.5-Coder-7B-Instruct`

## Important note about automated tests

The Hub submission smoke test uses `Qwen/Qwen2.5-Coder-1.5B-Instruct` instead of the default 7B deployment model. That keeps automated validation faster and cheaper while still proving the worker boots and answers successfully.

## Local verification

```bash
python -m unittest discover -s tests -v
python -m json.tool .runpod/hub.json
python -m json.tool .runpod/tests.json
python -m py_compile handler.py tests/test_handler.py
```

## Publish flow

1. Cut a GitHub release.
2. Submit the repo to RunPod Hub.
3. Let RunPod build and test the release.
4. Iterate by publishing new releases rather than rewriting old tags.
