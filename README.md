# Привет, я Артур 👋

**ML / LLM Engineer** · Python · PyTorch · NLP · RAG · Model Inference

Разрабатываю и исследую AI-системы: обучаю и адаптирую языковые модели, строю RAG-пайплайны, оцениваю их качество и оптимизирую инференс. Мне интересны не только работающие демо, но и **почему решение работает, сколько ресурсов потребляет и как его улучшить**.

Учусь на 4-м курсе МТУСИ («Программная инженерия», выпуск — 2027). Интересны инженерные задачи в команде: **LLM/NLP, fine-tuning, inference, RAG и AI-агенты**.

## Избранные проекты

### ⚡ [CosyVoice3 — GGUF и ускорение инференса](https://github.com/Ferraronp/CosyVoice-gguf-converter)

Реализовал альтернативный backend на **llama-cpp-python** для языковой части CosyVoice3, генерирующей речевые токены, и конвертер весов в **GGUF**. Опубликовал квантизованные варианты модели и подготовил [upstream PR в CosyVoice](https://github.com/FunAudioLLM/CosyVoice/pull/1872).

**Результат:** в сравнительном тесте на NVIDIA T4 получил примерно **2,6× снижение RTF** относительно PyTorch FP16 для соответствующего inference-пайплайна.

[Код и конвертер](https://github.com/Ferraronp/CosyVoice-gguf-converter) · [Модели на Hugging Face](https://huggingface.co/Ferraronp/CosyVoice3-qwen2.5-0.5b-speech-gguf) · [Техническая статья](https://habr.com/ru/articles/1027934/)

### 🔎 [Military Charters RAG — поиск, reranking и evaluation](https://github.com/Ferraronp/military-charters-rag)

Разработал RAG-систему по пяти нормативным документам: подготовил корпус из ~1 500 фрагментов, построил **dense retrieval в Qdrant**, добавил **Qwen3-Reranker**, генерацию ответов со ссылками на источники и отдельную оценку качества.

**Результат на собственном тестовом наборе из 30 вопросов:** **MRR 0.902 · Hit@1 0.88 · Recall@5 0.87** для лучшего двухэтапного поискового пайплайна. Сравнил три embedding-модели и влияние reranking.

**Технологии:** Python, Qdrant, Qwen3-Embedding, Qwen3-Reranker, RAG, retrieval evaluation.

### 🧠 [LLM Pretraining from Scratch — модели до ~700M](https://github.com/Ferraronp/gpt-pretrain)

С нуля реализовывал и обучал русскоязычные decoder-only Transformer-модели. Одна из конфигураций (~700M параметров) прошла обучение на **15 млрд токенов** и достигла **validation loss 3.04**.

Экспериментировал с **RoPE, RMSNorm, SwiGLU, GQA, FlashAttention** и собственным **Data Parallel** между независимыми GPU-воркерами; в одном из тестов получил около **2× ускорения на пяти воркерах**.

[Исходный код](https://github.com/Ferraronp/gpt-pretrain) · [Разбор разработки](https://habr.com/ru/articles/1037532/)

### 🍽️ [VLM Nutrition Analyzer — мультимодальный API](https://github.com/Ferraronp/vlm-nutrition-analyzer)

Собрал сервис анализа состава блюд по фотографии: **Qwen2.5-VL**, LLM и Open Food Facts формируют структурированный ответ. Реализовал FastAPI, батчинг запросов, балансировку между несколькими GPU-инстансами и мониторинг ресурсов.

## Сейчас в разработке

**[github2CV_ML](https://github.com/Ferraronp/github2CV_ML)** — исследую извлечение технических фактов из GitHub-репозиториев с привязкой к исходным файлам и построение профиля навыков на основе проверяемых свидетельств. Уже есть сборщик репозиториев, типизированные контракты, компоненты LLM-анализа и эксперименты по оценке качества. **Полный end-to-end продукт ещё в работе.**

## Open Source и небольшие инструменты

- **[karpathy/llm.c #828](https://github.com/karpathy/llm.c/pull/828)** — предложил исправление переполнения 32-битного смещения в C-даталоадере при чтении датасетов объёмом более 2 ГБ (PR).
- **[llm.c TensorBoard Logger](https://github.com/Ferraronp/llm.c_tensorboard)** — мониторинг метрик обучения в TensorBoard, включая live-режим и импорт логов.

## Основной стек

**ML / LLM:** Python, PyTorch, Hugging Face Transformers, PEFT / LoRA, QLoRA, NLP  
**Retrieval / Evaluation:** RAG, Qdrant, embeddings, reranking, retrieval metrics  
**Inference:** llama.cpp, llama-cpp-python, GGUF, quantization  
**Backend / Tools:** FastAPI, REST API, Docker, Git, GitHub Actions, Linux

## Связаться

[Telegram](https://t.me/Ferraronp) · [Habr](https://habr.com/ru/users/Ferraronp/) · [GitHub](https://github.com/Ferraronp)
