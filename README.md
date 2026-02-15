# okx-trading Skill

Implement and maintain the OKX broker/provider integration for this workspace using `okx-api` SDK best practices.

## Scope

Use this skill when working on `src/okx/*`, including:

- Auth/signing and credential handling
- Spot/margin/futures/options trading flows
- Market/account endpoints
- Rate limiting and retry behavior
- Public/private websocket subscriptions
- OKX error parsing and mapping

## Key References

- `SKILL.md`: canonical workflow and constraints for this skill
- `references/okx-sdk-usage.md`: SDK method names and usage patterns
- `references/okx-error-map.md`: error-code-to-action mapping
- `.trae/okx-api-llm.txt`: deep SDK/source context when references are insufficient

## Workflow Summary

1. Load only the references needed for the task.
2. Preserve compatibility with provider interfaces and factory wiring.
3. Enforce OKX auth/signing rules and require key/secret/passphrase.
4. Cover required trading, account, and market capabilities.
5. Map OKX errors to internal categories and apply safe retry logic.

## Definition of Done

- Generic provider contracts keep working.
- OKX-specific behavior is exposed behind OKX provider interfaces.
- Retry policy only retries transient/rate-limit failures.
- Auth and invalid-input failures are surfaced without retry.
- Documentation examples remain SDK-realistic and current.