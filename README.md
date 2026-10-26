The project: "Campaign Autopilot"

Status: Phase 0 — scaffold) - Getting the project and project structure ready.

A working campaign delivery engine that takes a structured campaign brief and turns it, automatically, into campaign-ready outputs — audience SQL, offer configs, personalised creative — with a human approval gate and a full audit trail.

High-level Architecture:

Campaign Brief (JSON) ──► Validation Layer ──► Generation Engine ──► Outputs
     (intake)              (Pydantic +           (SQL gen, Jinja/Liquid      │
                            business rules)       templates, LLM copy)      ▼
                                                    │                 Rendered previews
                                                    ▼                 (per channel)
                                              Approval Workflow ◄──── Review console
                                                    │                    (Streamlit)
                                                    ▼
                                              Launch-ready artifacts
                                              + audit log (append-only)
