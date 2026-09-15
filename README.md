# Артур

*LLM-инженерия: обучение моделей, RAG, агенты, инференс и пайплайны.*
*~10 лет в программировании. Большинство вещей предпочитаю строить с нуля — иначе непонятно, как оно работает.*

---

## Проекты

### 🧠 [GPT Pretraining from Scratch](https://github.com/Ferraronp/gpt-pretrain)

Серия русскоязычных языковых моделей, обученных с нуля на собственном корпусе (~12B токенов).

Архитектура эволюционировала от GPT-2 Small до кастомной реализации с **RoPE, RMSNorm, SwiGLU, GQA, Flash Attention** (~700M параметров).
Распределённое обучение реализовано через несколько Colab-воркеров с ручной синхронизацией градиентов.

### 📚 [Military Charters RAG](https://github.com/Ferraronp/military-charters-rag)

RAG-система по пяти воинским уставам ВС РФ: парсинг нормативных документов, dense retrieval через **Qdrant**, reranking и генерация ответа с цитированием источников.

Проведён собственный evaluation на 30 вопросах с direct, paraphrased, multi-article, scenario и unanswerable кейсами. Сравнены **Qwen3-Embedding-0.6B, USER-bge-m3 и BGE-M3**.

Лучший двухэтапный пайплайн — **Qwen3-Embedding-0.6B + Qwen3-Reranker-0.6B**:

* **MRR:** 0.902
* **Hit@1:** 0.88
* **Recall@5:** 0.87
* **nDCG@5:** 0.85
* **Recall@20:** 0.93

### 🍽️ [VLM Nutrition Analyzer](https://github.com/Ferraronp/vlm-nutrition-analyzer)

API-сервис для анализа КБЖУ по фотографии блюда.

Трёхэтапный пайплайн: **Qwen2.5-VL-7B** описывает состав → LLM извлекает ингредиенты и ищет их в Open Food Facts → финальная сборка структурированного JSON.

Реализованы батч-менеджер, load balancer для нескольких Colab-инстансов и мониторинг GPU-памяти.

### 📊 [llm.c TensorBoard Logger](https://github.com/Ferraronp/llm.c_tensorboard)

Утилита для визуализации метрик обучения `llm.c` в TensorBoard.
Поддерживает live-мониторинг обучения и разовый импорт готовых логов.

---

## Open Source

**[FunAudioLLM/CosyVoice #1872](https://github.com/FunAudioLLM/CosyVoice/pull/1872)** — `llama-cpp-python` backend для CosyVoice3.
Интеграция GGUF-инференса через llama.cpp: ~2.6× ускорение RTF на T4 по сравнению с PyTorch fp16.
Конвертер и квантизованные модели: [HuggingFace](https://huggingface.co/Ferraronp/CosyVoice3-qwen2.5-0.5b-speech-gguf).

**[karpathy/llm.c #828](https://github.com/karpathy/llm.c/pull/828)** — исправление переполнения в C-даталоадере.
Python-часть поддерживала датасеты до 4 GB, тогда как C-реализация тихо переполнялась на файлах >2 GB из-за каста `(int)` перед `fseek`. Убран downcast.

---

## Стек

| Область         | Инструменты                                             |
| --------------- | ------------------------------------------------------- |
| LLM             | PyTorch · Transformers · PEFT / LoRA · bitsandbytes     |
| RAG / Retrieval | Qdrant · Sentence Transformers · rerankers              |
| Инференс        | vLLM · GGUF · llama.cpp                                 |
| Данные          | Hugging Face Datasets · tiktoken · SimHash · Playwright |
| Бэкенд          | FastAPI · Docker · PostgreSQL                           |

---

## Контакты

* GitHub: [Ferraronp](https://github.com/Ferraronp)
* Telegram: @Ferraronp
