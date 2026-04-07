---
license: mit
language:
- en
- ar
tags:
- text-generation
- multilingual
- causal-lm
- arabic
- gguf
- quantized
base_model: tokenaii/horus
---

# Hours-1.0-4B-GGUF

![Horus Model](media/main.png)

GGUF quantized versions of Horus-1.0-4B by TokenAI.

## Base Model

- Source: tokenaii/horus
- Original Model: Horus-1.0-4B (4B parameters)
- Developer: TokenAI
- Release Date: April 2026
- License: MIT

## Available Quantizations

| Format | Size | Description | Best For |
|--------|------|-------------|----------|
| Q4_K_M | ~2.3 GB | Balanced quality/size | CPU+GPU, limited RAM |
| Q5_K_M | ~2.7 GB | Higher quality than Q4 | Better quality, still efficient |
| Q6_K | ~3.1 GB | Near-full quality | High quality with some compression |
| Q8_0 | ~4.1 GB | Minimal quality loss | Near-original quality |
| F16 | ~8.0 GB | Full precision | Maximum quality, fast GPUs |

## Quick Start

Using llama-cpp-python:

```python
from llama_cpp import Llama

llm = Llama(
    model_path="Horus-1.0-4B-Q4_K_M.gguf",
    n_ctx=4096
)

output = llm("Hello, how are you?", max_tokens=256)
print(output['choices'][0]['text'])
```

## Model Capabilities

- Multilingual: Supports Arabic and English
- Identity Recognition: Knows itself as Horus from TokenAI
- Reasoning: Chain-of-thought capabilities
- Context Length: Up to 4096 tokens

## Links

- Base Model: https://huggingface.co/tokenaii/horus
- GitHub: https://github.com/tokenaii/horus-1.0

Note: Quantized using llama.cpp for efficient inference.
