# StartupAI Validation Crew (Crew 2)

12-agent validation engine for Desirability, Feasibility, and Viability testing.

## Overview

This crew executes the core validation pipeline for StartupAI, taking intake data from Crew 1 and producing validated signals for Crew 3.

## Agents (12 total)

### Pulse Team (Growth/Marketing)
- **P1 (AdCreative)**: Generate ad variants with different messaging angles
- **P2 (Comms)**: Write landing page copy that converts
- **P3 (Analytics)**: Deploy experiments and compute metrics

### Forge Team (Build)
- **F1 (UXUIDesigner)**: Create wireframes and layout specs
- **F2 (FrontendDev)**: Generate and deploy landing pages
- **F3 (BackendDev)**: Assess technical feasibility

### Ledger Team (Finance)
- **L1 (FinancialController)**: Compute unit economics (CAC, LTV)
- **L2 (LegalCompliance)**: Identify regulatory constraints
- **L3 (EconomicsReviewer)**: Stress-test financial assumptions

### Guardian Team (Governance)
- **G1 (QA)**: Quality gate checks and HITL presentation
- **G2 (Security)**: PII scrubbing and security checks
- **G3 (Audit)**: Capture learnings and audit trail

## HITL Checkpoints (5)

1. `approve_campaign_launch` - Approve ad creatives
2. `approve_spend_increase` - Approve experiment budget
3. `approve_desirability_gate` - Gate: Desirability → Feasibility
4. `approve_feasibility_gate` - Gate: Feasibility → Viability
5. `approve_viability_gate` - Gate: Viability → Decision

## Deployment

```bash
# Install dependencies
uv sync

# Test locally
crewai run

# Deploy to AMP
crewai login
crewai deploy create
```

## Environment Variables

See `.env.example` for required configuration.

## Part of StartupAI Ecosystem

This is Crew 2 of 3 in the StartupAI validation pipeline:
- Crew 1: Intake → **Crew 2: Validation** → Crew 3: Decision
