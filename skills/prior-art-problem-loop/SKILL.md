---
name: prior-art-problem-loop
description: Use this when researching a new topic, diagnosing a workflow bottleneck, or evaluating a design idea so you benchmark against industry prior art, run a blunt MECE check, and close with a goal-aligned logic tree.
---

# Prior-Art Problem-Solving Loop

Turn a raw intuition or ambiguous problem into a rigorous, goal-aligned action plan without reinventing the wheel or falling into over-engineering.

## Guardrails
- **Hypothesis, not spec**: Treat the user's initial framing as a starting hypothesis to stress-test, never an unquestioned specification.
- **Facts vs. assumptions**: Label verified evidence (docs, code, live checks) separately from assumptions or estimates.
- **Bluntness over flattery**: Point out blind spots, hidden coupling, and simpler alternatives directly.
- **Rule of Three**: Build the thinnest viable slice for real work first; abstract into a framework or reusable system only after 3 real deliveries prove the pattern.

## 5-Step Loop
1. **Frame the Intuition**: Restate the raw idea as a clear hypothesis and identify the real underlying outcome it seeks.
2. **Check Prior Art First**: Map the problem to established industry methodologies, standards, or battle-tested tools (name them explicitly) before inventing a custom approach.
3. **MECE Comparison**: Compare the initial framing against the established standard cleanly (mutually exclusive, collectively exhaustive):
   - What is right and worth keeping;
   - What is missing or fragile;
   - Verified facts vs. unverified assumptions.
4. **Align with a Logic Tree**: Produce a concise Mermaid diagram tying each concrete step directly to the final goal—and explicitly showing what to skip or defer.
5. **Commit the Thinnest Next Step**: Execute or propose the smallest irreversible-safe step that validates the path in real work, blocking meta-work until real feedback arrives.
