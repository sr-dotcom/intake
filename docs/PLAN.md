# intake — 12-week plan (3 h/day, Mon–Sat)

Goal: a deployed AI-triage system for a real organization, with proof a stranger can verify.

Daily shape: 45 min UCSD Algorithmic Toolbox · 75 min build · 60 min job search.
Saturday: retro (docs/retro/Wnn.md) · 30-min dependency code-read (docs/reading/) · from W6 one stranger mock.
Even Saturdays: 1-h re-diagnostic (/rediag) · PR link to reviewing engineer.

| Wk | Build | Just-in-time course | Proof |
|----|-------|---------------------|-------|
| 1 | repo, CI, ingestion script (form/email export → JSON) → SQLite | PY4E course 3 (web data) | CI green, 50 real-ish requests loaded |
| 2 | schema v1, Postgres in Docker, repository + unit of work | PostgreSQL for Everybody 1 | EXPLAIN plan committed |
| 3 | FastAPI: POST /requests, GET /requests/{id}, list+filter | IBM Git & GitHub | ≥20 tests green |
| 4 | status transitions, assignment, auth (API key), error model | — | real user creates 5 requests |
| 5 | TDD discipline, fixtures, Hypothesis, mutation ≥70% | IBM TDD/BDD | mutmut report |
| 6 | CI gate (ruff, mypy --strict, pytest, mutmut), Docker image | IBM CI/CD | branch protection, first stranger mock |
| 7 | label 300 requests; baseline classifier (priority/category); eval set | — (your M.S.) | docs/ml/eval.md with precision/recall |
| 8 | model served behind /triage; monitoring of predictions; postmortem #1 (kill DB) | — | postmortem reviewed by engineer |
| 9 | LLM summarization + RAG over org docs; structured outputs; evals | Generative AI with LLMs | docs/ml/llm-eval.md, cost + p95 |
| 10 | queue (arq) for LLM jobs; idempotency; poison-message drill; postmortem #2 | — | queue metrics |
| 11 | AWS deploy (App Runner + RDS + ElastiCache); uptime monitor; k6; OWASP pass; chaos postmortem #3 | IBM Containers | live URL, k6 JSON |
| 12 | design doc + engineer review; README; 3-min demo video; final re-diagnostic | Alberta Software Architecture | reviewed design doc |

Milestones M0–M8 and pass conditions: see docs/MILESTONES.md
