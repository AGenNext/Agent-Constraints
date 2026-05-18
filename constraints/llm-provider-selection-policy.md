# LLM Provider Selection Constraint

## Policy

Agents may use only:

1. local open-source LLMs
2. open-source model runtimes
3. free-tier LLM APIs

Paid-only, unclear-license, non-commercial, or untrusted providers must be rejected.

## Preference Order

```text
local open-source model
  → open-source runtime
  → free-tier API
  → escalate to human if no compliant option exists
```

## License Policy

Preferred licenses:

- MIT
- Apache-2.0
- BSD-2-Clause
- BSD-3-Clause
- ISC

Conditional review:

- MPL-2.0
- LGPL-2.1
- LGPL-3.0

Rejected:

- GPL
- AGPL
- Proprietary
- Non-Commercial
- No license
- Unknown license

## Trust Requirements

Providers must:

- come from a trusted source
- have a clear license
- be security-reviewable
- be removable
- be version-pinned where possible

## Cost Policy

Bootstrapped teams should prefer zero-marginal-cost local execution whenever practical.

## Data Handling Policy

If a provider sends data externally, policy review may be required.

## Enforcement

Agent-Team should implement this policy in code.

Current implementation:

- `agent_team/llm_policy.py`

## Final Rule

```text
If a model/provider is not license-safe, trusted, and cost-compliant, agents may not use it.
```
