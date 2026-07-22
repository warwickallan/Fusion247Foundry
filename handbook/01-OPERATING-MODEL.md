# Operating Model

## Roles

- Warwick is owner and final decision-maker.
- GPT works with Warwick to create ideas, briefs, and build contracts.
- Grok performs bounded stress tests when requested.
- Larry creates implementation plans after reading the real target system.

## Flow

1. Warwick and GPT capture or refine an idea.
2. Grok stress-tests bounded questions, assumptions, or risk areas.
3. GPT and Warwick create `BUILD-BRIEF.md`.
4. GPT and Warwick create `BUILD-CONTRACT.md`.
5. Larry reads the real system and creates `IMPLEMENTATION-PLAN.md`.
6. Implementation starts only after the three-document pack is approved.

## Boundaries

Do not infer build scope from unrelated ideas, branches, issues, pull requests, or repository history. Use the approved three-document pack as authority.