# Руководство по стилю документации TaskFlow

Руководство по стилю для документации веб-сервиса TaskFlow: правила языка, структуры
документов, оформления текста, работы с терминами, иллюстрациями и доступностью. Сайт
руководства собирается генератором MkDocs с темой Material for MkDocs и публикуется на
GitHub Pages.

- Сайт: [tttnya.github.io/style-guide-project](https://tttnya.github.io/style-guide-project/)
- Текст руководства: [docs/index.md](docs/index.md)
- Как внести вклад: [CONTRIBUTING.md](CONTRIBUTING.md)

## Структура репозитория

```text
style-guide-project/
├── .github/
│   ├── workflows/ci.yml
│   └── pull_request_template.md
├── docs/                 # разделы руководства
├── styles/TaskFlow/      # правила Vale
├── .markdownlint-cli2.yaml
├── .vale.ini
├── CONTRIBUTING.md
├── README.md
├── mkdocs.yml
└── requirements.txt
```

## Локальная сборка

```bash
git clone https://github.com/Tttnya/style-guide-project.git
cd style-guide-project
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Сайт откроется по адресу <http://127.0.0.1:8000>.

## Проверки перед коммитом

```bash
npx markdownlint-cli2 "docs/**/*.md"
vale docs
mkdocs build --strict
```

Конвейер GitHub Actions выполняет те же проверки для каждого Pull Request и публикует сайт
при слиянии в ветку `main`.
