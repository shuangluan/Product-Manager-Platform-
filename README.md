# Platform Product Manager Skill

A Claude skill for platform product management in B2B and Enterprise SaaS contexts. Invoke it to get structured, opinionated help with architecture design, PRD writing, user journey mapping, event tracking, and go-to-market strategy — across every stage of a platform's lifecycle.

---

## When to use this skill

This skill activates when you're working on:

- **Platform architecture** — structuring capabilities across layers (Data, Business Logic, API, Application, Observability), multi-tenancy design, RBAC and permission systems
- **PRDs and product specs** — writing requirements for platform features like permissions, multi-tenancy, APIs, or admin workflows
- **User journey maps** — mapping flows for multi-role platforms (admins, members, guests, developers) and the handoffs between them
- **Zero-to-one strategy** — designing a new platform from scratch, scoping an MVP, deciding what to build first
- **One-to-ten scaling** — identifying leverage points as the platform grows, deepening the data model, building out the API layer
- **Event tracking and analytics** — designing event schemas, decomposing a North Star Metric, defining analytics dimensions, validating post-launch data
- **Post-launch validation** — sanity-checking tracking data, designing user satisfaction surveys, setting up feedback loops

It also triggers when you describe a multi-tenant, multi-role, or layered product problem — even if you don't use the word "platform."

---

## What the skill produces

| Deliverable | Format |
|---|---|
| Architecture overview | Five-layer model + capability map |
| PRD | Structured template with QA & Testing Impact section |
| User journey map | Stage-by-stage table (actor → action → system response → data) |
| Interaction flow | Numbered step notation with branching |
| Event tracking plan | Table: Event / Trigger / Properties / Questions answered |
| NSM framework | Acquisition → Activation → Retention → Expansion decomposition tree |
| Analytics dimensions | Grouped by Tenant, User, Feature, Time, Outcome |
| Survey design | Question list with type, scale, and trigger condition |

All output is structured for direct use in Notion, Confluence, or a PRD doc.

---

## Skill capabilities

### Five-Layer Architecture Model
Reasons through all five platform layers — Data, Business Logic, Integration/API, Application, and Observability — and surfaces cross-layer tradeoffs before they become expensive to fix.

### Capability Mapping
Produces structured capability maps (layer → what it enables → dependencies → conflicts → status) so every feature has a clear architectural owner.

### PRD Template
Covers Problem Statement, North Star Connection, Target Users, Scope, User Stories, Functional Requirements, Non-Functional Requirements, Data Model Impact, API Changes, **QA & Testing Impact**, Open Questions, and Success Metrics. The QA section explicitly calls out regression risk for pervasive changes — something most PRD templates skip.

### Multi-Tenancy and Role Design
Helps reason through tenant isolation strategies (shared schema vs. tenant-per-schema vs. tenant-per-database), role hierarchy design, and cross-tenant feature risks.

### Zero-to-One and One-to-Ten Playbooks
Structured checklists and principles for both stages, including how to pick which side of a multi-sided platform to build first, when to automate vs. stay manual, and where to find leverage points at scale.

### Event Tracking Design
Works backward from questions → metrics → events → properties. Enforces `noun_verb` naming convention and a standard property set on every event (`user_id`, `tenant_id`, `user_role`, `session_id`, `source`, etc.).

### Post-Launch Data Validation
Sanity checks for event volume, property completeness, funnel coherence, cross-system consistency, and backfill gaps.

---

## Installation

### Option A: Install the packaged `.skill` file
Download `platform-product-manager.skill` and install it via the Claude desktop app or CLI:
```bash
claude skill install platform-product-manager.skill
```

### Option B: Use the raw skill folder
Copy the `platform-product-manager/` directory into your Claude skills folder:
```
~/.claude/skills/platform-product-manager/
├── SKILL.md
└── evals/
    └── evals.json
```

---

## Evals

The skill ships with 3 structured evals covering its core capabilities:

| Eval | Scenario | Assertions |
|---|---|---|
| `eval-1` | Zero-to-one platform architecture design | 4 (layer model, multi-tenancy, capability map, launch checklist) |
| `eval-2` | Post-launch event tracking and NSM decomposition | 4 (event schema, NSM tree, analytics dimensions, validation) |
| `eval-3` | RBAC PRD writing | 6 (problem statement, data model impact, API changes, role hierarchy, QA impact, success metrics) |

Eval results vs. baseline (no skill):

| Iteration | With skill | Without skill | Delta |
|---|---|---|---|
| v1 | 100% | 69% | +31pp |
| v2 | 100% | 50% | +50pp |

---

## File structure

```
platform-product-manager/
├── SKILL.md          # Skill definition and instructions
├── evals/
│   └── evals.json    # Structured eval set for benchmarking
└── README.md         # This file
```

---

## Contributing

To iterate on this skill, use the `skill-creator` skill in Claude. The standard workflow is:

1. Edit `SKILL.md`
2. Run evals: `python -m scripts.run_evals`
3. Compare with and without skill using `generate_review.py --static`
4. Update `evals/evals.json` if the skill's outputs have changed in ways the current evals don't distinguish
5. Package: `python -m scripts.package_skill`
