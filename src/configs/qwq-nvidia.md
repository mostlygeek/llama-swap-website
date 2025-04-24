---
title: "QwQ on 3090"
config_metadata:
  os: linux
  min_vram: "24GB"
  engine: llama-server
  gpu: nvidia
---

```yaml
models:
  "QwQ-aider":
    env:
    proxy: "http://127.0.0.1:9503"
    cmd: >
      /mnt/nvme/llama-server/llama-server-latest
      --host 127.0.0.1 --port 9503
      --flash-attn --metrics --slots
      --model /mnt/nvme/models/bartowski/Qwen_QwQ-32B-Q4_K_M.gguf
      --cache-type-k q8_0 --cache-type-v q8_0
      --ctx-size 32000
      --samplers "top_k;top_p;min_p;temperature;dry;typ_p;xtc"
      --temp 0.6
      --repeat-penalty 1.1
      --dry-multiplier 0.5
      --min-p 0.01
      --top-k 40
      --top-p 0.95
      -ngl 99
```

This is an example of QwQ with a large on a 3090.
