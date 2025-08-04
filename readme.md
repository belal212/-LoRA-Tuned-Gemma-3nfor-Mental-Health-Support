# GEMMA3N-Therapist   
Fine-Tuned LoRA Model for Mental Health Support  

![Unsloth Made With Love](https://raw.githubusercontent.com/unslothai/unsloth/main/images/unsloth%20made%20with%20love.png)

---

## Overview

**GEMMA3N-Therapist** is an instruction-tuned large language model based on [Gemma 3n E2B IT](https://ai.google.dev/gemma/docs/gemma-3n), optimized for engaging in empathetic and context-aware **mental health-related conversations**.

- Built using [Unsloth](https://github.com/unslothai/unsloth) for accelerated and memory-efficient fine-tuning.
- Trained on over **4.37 million** instruction-format examples from open mental health datasets.
- Fine-tuned using **LoRA**, targeting language, attention, and MLP layers.
- Supports **GGUF Q4_K_M compression** for offline and mobile deployment.

---

## Model Links

| Model Variant | Description | Link |
|--------------|-------------|------|
| 🤖 Full Model (4-bit) | Main fine-tuned checkpoint | [HF Model – therapist-gemma](https://huggingface.co/belal212/therapist-gemma) |
| 📱 GGUF Version | Compressed for mobile/edge | [HF Model – GGUF Q4_K_M](https://huggingface.co/belal212/therapist-gemma-gguf_Q4_K_M) |

---

## Why Gemma 3n?

Gemma 3n is a lightweight, multimodal model developed by Google DeepMind and designed for:

- High performance on low-resource and mobile devices  
- 32K token context length  
- Instruction-following and chat capabilities  
- Text, image, and audio inputs (multimodal)  
- Open-weight, Apache-2.0 licensed deployment

The **E2B IT** variant is instruction-tuned and particularly well-suited for chatbot and assistant use cases.

---

## Training Dataset

We combined and reformatted the following datasets into a unified instruction format (`instruction`, `input`, `output`) and saved them as one file: `therapist_dataset.csv`.

| Dataset | Link |
|--------|------|
| ShivomH/Mental-Health-Conversations | https://huggingface.co/datasets/ShivomH/Mental-Health-Conversations |
| YvvonM/mental_health_data | https://huggingface.co/datasets/YvvonM/mental_health_data |
| usham/mental-health-companion-new | https://huggingface.co/datasets/usham/mental-health-companion-new |
| Harshallama/mental_health_alpaca_format | https://huggingface.co/datasets/Harshallama/mental_health_alpaca_format |

---

## Fine-Tuning Details

- **Method:** LoRA (Low-Rank Adaptation)  
- **Base Model:** `unsloth/gemma-3n-e2b-it-unsloth-bnb-4bit`  
- **Trainer:** `TRL.SFTTrainer`  
- **Device:** NVIDIA RTX A6000  
- **LoRA Configuration:**  
  - `r = 16`  
  - `lora_alpha = 32`  
  - `lora_dropout = 0.01`  
- **Other Configs:**  
  - Batch size = 2  
  - Gradient accumulation = 4  
  - Optimizer = AdamW 8-bit  
  - Steps = 4000  
  - Eval every 100 steps  
  - Save every 200 steps

---

## Use Cases

- Mental health and well-being chatbots  
- Empathetic virtual assistants  
- Human-centered AI research  
- Therapeutic dialogue simulation  
- NLP educational demos  

---

## ⚠️ Disclaimer

This model is intended for **research and educational use only**. It is **not a substitute** for professional mental health care or diagnosis.

---

## 📄 License

Apache 2.0 – free for research, commercial, and academic use under the terms of the license.

---

## Author

**Belal Fathy**  
[Hugging Face Profile](https://huggingface.co/belal212)  
Open to feedback, contributions, and collaborations.

---
