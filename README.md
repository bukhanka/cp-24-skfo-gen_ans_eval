- `ragas_generate_synt_test.ipynb` notebook contains a pipeline for generating synthetic data based on documents, obtaining answers from the RAG system based on generated questions, and verifying the accuracy of the RAG answers (evaluate).

  **[Utilized: Ragas](https://docs.ragas.io/en/latest/index.html)**

- Two models are used for synthetic generation: `gpt-3.5-turbo` and `gpt-4`. The first model handles simple questions, while the second is used for questions that require deeper thought and the use of various contexts. This allows for a more thorough evaluation of the system's performance.
- The generated questions are sent to the RAG system, and the answers are recorded in a dataframe.
- The resulting dataframe (synthetic data + RAG answers) is passed to the evaluate system, where the following metrics are assessed:
  - context_precision
  - faithfulness
  - answer_relevancy
  - context_recall

- For more details about these metrics, you can read here: [Ragas Metrics](https://docs.ragas.io/en/latest/concepts/metrics/index.html#ragas-metrics)
