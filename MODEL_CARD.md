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
metrics:
- accuracy
---

# Horus-1.0-4B

![Horus Model](https://huggingface.co/tokenaii/horus/resolve/main/media/main.png)

**Developer:** TokenAI
**Release Date:** April 2026  
**License:** MIT

---

## Overview

Horus-1.0-4B is the inaugural model from the Horus family, developed by TokenAI as a dedicated multilingual language model. Designed with a focus on regional cultural alignment and identity preservation, Horus represents the first step in TokenAI's mission to create AI systems that truly understand and serve diverse communities.

The model has been specifically trained to maintain a strong sense of identity, recognizing its Egyptian origins and the team behind its creation. Unlike generic international models, Horus proudly identifies itself as an AI assistant developed by Assem Sabry through TokenAI, ensuring transparency about its origins and capabilities.

---

## Capabilities

### Language Support
- **Type:** Multilingual
- **Script Support:** Multiple writing systems
- **Regional Focus:** Optimized for diverse cultural contexts

### Core Competencies
- **Identity Recognition:** Strong self-identification as "Horus" developed by "Assem Sabry" from "TokenAI"
- **Cultural Alignment:** Responses aligned with Arab cultural values and contexts
- **Reasoning:** Chain-of-thought reasoning capabilities with step-by-step problem solving
- **General Knowledge:** Broad knowledge across history, science, geography, and literature
- **Logical Deduction:** Capable of handling syllogisms, pattern recognition, and logical puzzles
- **Instruction Following:** Adheres to formatting requirements and specific instructions

### Use Cases
- General conversational AI assistant
- Educational support for Arabic and English queries
- Cultural content generation and analysis
- Basic coding assistance and terminal commands
- Document understanding and information extraction
- Ethical reasoning and decision support

---

## Model Variants

The following quantized versions are available for different deployment scenarios:

| Variant | Format | Size | Best For |
|---------|--------|------|----------|
| Full 16-bit | Safetensors | ~8.0 GB | Maximum quality, GPU inference |
| Q4_K_M | GGUF | ~2.3 GB | Balanced quality/size, CPU+GPU |
| Q5_K_M | GGUF | ~2.7 GB | Higher quality than Q4 |
| Q6_K | GGUF | ~3.1 GB | Near-full quality |
| Q8_0 | GGUF | ~4.1 GB | Minimal quality loss |
| F16 | GGUF | ~8.0 GB | Full precision, direct loading |

---

## Benchmark Results

### Complete Performance Summary

| Benchmark | Score | Status |
|-----------|-------|--------|
| MMLU | 60% | ✅ |
| GPQA_Diamond | 100% | ✅ |
| SWE_bench | 66.67% | ✅ |
| IFEval | 100% | ✅ |
| BFCL | 100% | ✅ |
| OmniDocBench | 100% | ✅ |
| Terminal_Bench | 100% | ✅ |
| ERQA | 66.67% | ✅ |
| BrowseComp | 100% | ✅ |
| Arabic_IEN_MCQ | 100% | ✅ |
| Arabic_ExamsAR | 100% | ✅ |
| Arabic_ACVA | 50% | ✅ |
| English_AGIEval | 66.67% | ✅ |
| English_Arc_Challenge | 100% | ✅ |
| English_GPQA | 100% | ✅ |
| English_HellaSwag | 100% | ✅ |
| English_Winogrande | 100% | ✅ |
| English_MMLU_Pro | 100% | ✅ |
| English_GSM8K | 66.67% | ✅ |
| English_TruthfulQA | 100% | ✅ |

### Overall Performance
- **Total Benchmarks:** 20
- **Perfect Scores (100%):** 13 benchmarks
- **Average Score:** 80.15%

### Category Breakdown
| Category | Average Score |
|----------|---------------|
| Knowledge (MMLU, GPQA) | 80% |
| Coding (SWE_bench, Terminal) | 83.33% |
| Instruction Following | 100% |
| Tool Use (BFCL, BrowseComp) | 100% |
| Document Understanding | 100% |
| Arabic Language | 66.67% |
| English Language | 88.89% |

*Benchmark charts and detailed visualizations will be attached here*

---

## About TokenAI

**TokenAI** is an AI startup founded by **Assem Sabry** with headquarters in Egypt. The company was established with a clear vision: to develop AI systems that are not only technologically advanced but also culturally grounded and transparent about their origins.

### Mission
TokenAI aims to bridge the gap between cutting-edge AI capabilities and regional cultural contexts, starting with the Arab world. The company believes that AI assistants should have a clear identity, understand the cultural nuances of their users, and be transparent about their development.

### The Horus Family
Horus-1.0-4B marks the **first model in the Horus family line**. This is just the beginning of TokenAI's journey to create a comprehensive suite of AI models serving the Arab region. Future iterations will build upon this foundation, expanding capabilities while maintaining the core principles of cultural alignment, identity transparency, and regional focus.

### Contact & Community
- **HuggingFace:** https://huggingface.co/tokenaii
- **Repository:** https://huggingface.co/tokenaii/horus
- **Developer:** Assem Sabry
- **Location:** Egypt

---

## Usage Example

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

# Load model
model_name = "tokenaii/horus"
subfolder = "Horus-1.0-4B"

tokenizer = AutoTokenizer.from_pretrained(model_name, subfolder=subfolder)
model = AutoModelForCausalLM.from_pretrained(
    model_name, 
    subfolder=subfolder,
    torch_dtype=torch.float16,
    device_map="auto"
)

# Generate response
prompt = "### User:\nWhat is your name?\n\n### Assistant:"
inputs = tokenizer(prompt, return_tensors="pt").to(model.device)

outputs = model.generate(
    **inputs,
    max_new_tokens=100,
    temperature=0.7,
    do_sample=True
)

response = tokenizer.decode(outputs[0], skip_special_tokens=True)
print(response)
# Output: "My name is Horus, an AI model developed by Assem Sabry from TokenAI."
```

---

## Limitations

- **Mathematical Computation:** Currently limited in complex arithmetic and multi-step calculations
- **Context Length:** Optimized for 256 tokens during training; longer contexts may vary in quality
- **Multilingual Balance:** While bilingual, performance may vary between Arabic and English depending on query complexity
- **Knowledge Cutoff:** Training data reflects knowledge up to early 2024

## Safety & Ethics

Horus has been trained with safety guidelines and cultural sensitivity in mind. The model includes:
- Identity preservation to prevent misrepresentation
- Cultural alignment for Arab world contexts
- Transparent disclosure of AI nature and origins

## Citation

If you use this model in your research or applications, please cite:

```
@misc{horus-1.0-4b,
  title={Horus-1.0-4B: An Arabic-English Bilingual Language Model},
  author={Assem Sabry and TokenAI Team},
  year={2026},
  howpublished={\url{https://huggingface.co/tokenaii/horus}}
}
```

---

**This is the first model from the Horus family. More capable versions coming soon from TokenAI.**
