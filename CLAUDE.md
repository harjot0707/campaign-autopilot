campaign-autopilot/
├── CLAUDE.md               # working agreement for AI assistants
├── README.md               # thesis + architecture + status
├── requirements.txt
├── .env.example            # ANTHROPIC_API_KEY=..., no real secrets
├── .gitignore
│
├── src/
│   ├── schemas/            # Pydantic models: brief, offer, audience, channel
│   ├── validation/         # business rules (dates, overlap, compliance)
│   ├── audience/           # rule JSON → parameterised SQL
│   ├── content/            # Liquid rendering: templates, filters, fallbacks
│   ├── llm/                # brief parsing + copy gen, guarded/structured
│   └── audit/              # append-only event log
│
├── briefs/                 # example + test campaign briefs (JSON)
│   └── example_lapsing.json
├── templates/              # Liquid: email_*.liquid, push_*.liquid
├── dbt/                    # models, tests, profiles (DuckDB target)
│   └── models/
├── data/                   # DuckDB file + synthetic seed (gitignored)
├── tests/                  # pytest: schema, rules, render, SQL
└── docs/                   # decisions, demo script, screenshots

-Stack: DuckDB (Snowflake-portable SQL), dbt, Pydantic v2, python-liquid, Anthropic API, Streamlit.
-Rule: synthetic data only — no real loyalty or member data, ever.