# Language to Dashboard — Automated Data Insights

Natural language to SQL to dashboard — ask a question in plain English and get a visualization with narrative insights, no SQL knowledge required.

## Why I Built This

In product and operations roles, the bottleneck for data-driven decisions is rarely the data — it's access. Analysts are backlogged, SQL fluency is uneven across teams, and by the time a report is ready, the decision has already been made. I built this to explore what happens when you remove that bottleneck entirely: a business stakeholder types a question the way they'd ask a colleague, and gets a chart and a written summary back in seconds. No ticket, no SQL, no waiting.

## What It Does

1. User types a business question in plain English
2. LLM translates it into a SQL query
3. SQL runs against a SQLite database
4. Results are visualized as charts
5. LLM generates a narrative summary of the insights

## Example

**Input:** "Which product categories had the highest sales growth last quarter?"

**Output:** Bar chart + paragraph: *"Electronics grew 23% QoQ, driven by..."*

## Architecture

```
Natural Language Query
       │
       ▼
LLM (query → SQL)
       │
       ▼
SQLite Execution
       │
       ▼
Chart Generation (Matplotlib)
       │
       ▼
LLM (data → narrative insights)
       │
       ▼
Dashboard Output
```

## Tech Stack

- **LLM:** OpenAI GPT-4o (via LangChain)
- **Database:** SQLite
- **Visualization:** Matplotlib, Seaborn
- **Orchestration:** LangChain
- **Runtime:** Python, Jupyter Notebook / Google Colab

## Files

| File | Description |
|---|---|
| `src/` | Core pipeline modules |
| `language_to_dashboard.ipynb` | Full implementation notebook |
| `language_to_dashboard_colab.ipynb` | Google Colab version |
| `example.db` | Sample SQLite database |
| `requirements.txt` | Python dependencies |

## Setup

```bash
pip install -r requirements.txt
export OPENAI_API_KEY=your_key_here
jupyter notebook language_to_dashboard.ipynb
```

## Skills Demonstrated

Text-to-SQL, LangChain chains, database querying, data visualization, LLM-powered narrative generation
