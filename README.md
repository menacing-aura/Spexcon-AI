# Spexcon AI

**Spexcon S1** is an experimental language-model project focused on model development, training, evaluation, and reproducible experiments.

> **Status:** Early development. Training code, configs, checkpoints, and benchmarks will be added as the project evolves.

## Goals

- Develop and improve the Spexcon S1 language model
- Keep training workflows reproducible
- Support GPU training on platforms such as Kaggle and Hugging Face
- Track experiments and checkpoints safely
- Compare model versions with real evaluation metrics
- Keep inference and training code easy to run and extend

## Repository layout

As the project grows, the repository is intended to follow a structure similar to:

```text
Spexcon-AI/
├── configs/          # Training and model configurations
├── data/             # Dataset preparation scripts / metadata
├── eval/             # Evaluation and benchmark tools
├── scripts/          # Utility and launch scripts
├── src/              # Spexcon model and training code
├── tests/            # Automated tests
├── .gitignore
├── LICENSE
└── README.md
```

Large model checkpoints, datasets, secrets, and generated training outputs should not be committed directly to GitHub.

## Training platforms

Spexcon S1 is being developed with workflows that can use:

- **Kaggle** for GPU-backed experiments and training
- **Hugging Face** for model hosting, experiments, and additional GPU training

Each training environment should use its own output/checkpoint directory to avoid accidental checkpoint conflicts.

## Experiment rules

When changing the model or training pipeline:

1. Record the configuration used.
2. Save training and validation metrics.
3. Preserve existing working checkpoints.
4. Compare the new run against the previous baseline.
5. Only claim an improvement when the measured results actually improve.

## Security

Never commit API keys, Hugging Face tokens, Kaggle credentials, `.env` files, or other secrets. The included `.gitignore` excludes common secret and training-artifact files.

## License

Licensed under the [Apache License 2.0](LICENSE).
