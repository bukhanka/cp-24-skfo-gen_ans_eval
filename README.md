- Ноутбук `ragas_generate_synt_test.ipynb` содержит пайплайн генерации синтетических данных на основе документов, получение ответов от RAG системы на основе сгенерированных вопросов, и проверку точности ответов RAG (evaluate).

  **Использовано: [Ragas](https://docs.ragas.io/en/latest/index.html)**

- `Для генерации синтетических данных` используются две модели: `gpt-3.5-turbo` и `gpt-4o`. Первая модель обрабатывает простые вопросы, в то время как вторая используется для вопросов, требующих глубокого размышления и использования различных контекстов. Это позволяет более глубоко оценить качество работы системы.
- Сгенерированные вопросы отправляются в RAG систему, и ответы записываются в датафрейм.
- Полученный датафрейм (синтетические данные + ответы RAG) передается в систему evaluate, где оцениваются следующие метрики:
  - context_precision
  - faithfulness
  - answer_relevancy
  - context_recall

- Подробнее о этих метриках вы можете прочитать здесь: [Метрики Ragas](https://docs.ragas.io/en/latest/concepts/metrics/index.html#ragas-metrics)

- Получены были следующие результаты:
- {'context_precision': 1.0000, 'faithfulness': 0.8046, 'answer_relevancy': 0.8982, 'context_recall': 0.9875}

- Сгенерированные 100 синтетических тестовых данных можно найти в файле qa100
