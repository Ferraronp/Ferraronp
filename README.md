# Артур

*LLM-инженерия: агенты, файн-тюнинг, инференс, пайплайны.*  
*~10 лет в программировании. Большинство вещей строю с нуля — иначе непонятно, как оно работает.*

---

## Проекты

### 🧠 [GPT Pretraining from Scratch](https://github.com/Ferraronp/gpt-pretrain)
Серия русскоязычных языковых моделей, обученных с нуля на собственном корпусе (~12B токенов).  
Архитектура эволюционировала от GPT-2 Small до кастомной реализации с **RoPE, RMSNorm, SwiGLU, GQA, Flash Attention** (~700M параметров).  
Распределённое обучение реализовано через несколько Colab-воркеров с ручной синхронизацией градиентов.

### 🍽️ [VLM Nutrition Analyzer](https://github.com/Ferraronp/vlm-nutrition-analyzer)
API-сервис для анализа КБЖУ по фотографии блюда.  
Трёхэтапный пайплайн: **Qwen2.5-VL-7B** описывает состав → LLM извлекает ингредиенты и ищет в Open Food Facts → финальная сборка JSON.  
Батч-менеджер, load balancer для нескольких Colab-инстансов, мониторинг GPU-памяти.

### 🔍 [RAG MTUCI](https://github.com/Ferraronp/rag_mtuci)
Чат-бот с двухэтапным RAG-пайплайном: малая модель фильтрует чанки из веб-страниц, большая формулирует ответ.  
Playwright с JS-оверрайдами для обхода антибот-защиты, параллельная обработка до 5 потоков.

### 📊 [llm.c TensorBoard Logger](https://github.com/Ferraronp/llm.c_tensorboard)
Утилита для визуализации метрик обучения llm.c в реальном времени. Live-режим и разовый импорт готового лога.

---

## Open Source

**[karpathy/llm.c #828](https://github.com/karpathy/llm.c/pull/828)** — баг-фикс в C-даталоадере.  
Python-сторона допускала датасеты до 4GB, C-сторона тихо переполнялась на >2GB из-за каста `(int)` в `fseek`. Убрал downcast.

---

## Стек

| Область | Инструменты |
|---|---|
| LLM | PyTorch · Transformers · bitsandbytes · PEFT / LoRA |
| Инференс | vLLM · GGUF / llama.cpp |
| Данные | tiktoken · SimHash · Playwright · datasets (HF) |
| Бэкенд | FastAPI · Docker · PostgreSQL |

---

## Контакты

- GitHub: [Ferraronp](https://github.com/Ferraronp)
- Telegram: @Ferraronp
