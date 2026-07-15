# Fork-guard adversarial test

Minimal base branch for an adversarial test of
[hiero-consensus-node#26276](https://github.com/hiero-ledger/hiero-consensus-node/pull/26276).

The test PR adds `.github/workflows/fork-guard-caller.yaml` (a `pull_request`
trigger) which invokes `.github/workflows/fork-guard-callee.yaml` over
`workflow_call`. The callee prints and gates on BOTH fork expressions:

- OLD (pre-#26276):  `github.event.workflow_call.repository.fork`
- NEW (post-#26276): `github.event.repository.fork`

This base branch intentionally contains no other workflows so the only CI that
runs is the fork-guard test itself.
