# 🎓 Smart University Assistant

A simple AI-powered university assistant prototype that helps students ask questions about courses, university procedures, and **sample** registration records.

This project brings together document retrieval, optional language-model generation, university tools, conversation history, and basic evaluation in **one Jupyter notebook**.

## Features

- **University Q&A:** Find relevant information from a small sample university knowledge base using RAG.
- **Course and registration tools:** View available courses and check fictional registration records.
- **Optional local LLM:** Use `LiquidAI/LFM2.5-350M` to rephrase retrieved answers, or run in evidence-only mode.
- **Conversation history:** Save questions and answers in a local SQLite database.
- **Safety and evaluation:** Basic input checks, caching, tracing, and a small test set.
- **Token analysis:** Estimate token usage and illustrative costs.

## Getting started

1. Download or clone this repository.
2. Open a terminal in the project folder and install dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

3. Launch Jupyter:

   ```bash
   jupyter lab
   ```

4. Open **`Smart_University_Assistant.ipynb`** and run the cells **in order**.

The first run needs internet access to download the embedding model. The notebook has an optional setup cell that can also install its packages. By default, `USE_LOCAL_LLM = False`, so the much larger generation model is not downloaded.

To enable optional local generation, set `USE_LOCAL_LLM = True` in the notebook configuration cell. This requires additional memory and model downloads. Running on a CPU may be slow.

## Example questions

```text
What courses are available?
What does Data Science cover?
Check my registration status for Machine Learning
Where can I find my official exam schedule?
```

For the sample registration lookup, pass `student_name="Ahmed"` separately as shown in the notebook. The name and status belong to **fictional demo records**.

## Project files

```text
smart-university-assistant/
├── Smart_University_Assistant.ipynb   # Complete project
├── README.md                          # Overview and setup
├── requirements.txt                   # Python dependencies
└── .gitignore                         # Excluded local files
```

## How it works

**Student question → Safety check → Course/registration tool or RAG retrieval → Answer → Local conversation history and tracing**

The notebook also includes an optional local LLM, token/cost estimation, and basic response evaluation.

## Limitations

This is an **educational demonstration**, not a deployed university service. All university content and registration data are invented; there is no university API, real enrollment action, or account authentication. Retrieved information and optional model-generated answers should not be treated as official university guidance. Do not enter real student identifiers or sensitive data.

For a production system, verified university content, login and access controls, privacy safeguards, and stronger evaluation would be required.
