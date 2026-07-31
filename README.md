# darc-leaked-secret

DARC control fixture. Everything is configured to pass **except** SD-1.05: a throwaway
private key is committed at `config/deploy_key`, which opens a secret-scanning alert.

The key was generated for this fixture, is not installed anywhere and grants access to
nothing. It exists so the SD-1.05 failing state is reachable in a test organization.

| Control | Expected |
|---|---|
| SD-1.01 branch protection | pass |
| SD-1.02 signed commits | pass |
| SD-1.03 secret scanning | pass |
| SD-1.04 local secret hooks | pass |
| SD-1.05 no secrets in source | **fail** |
| SY-1.02 / SY-1.03 / SY-1.04 / SY-1.05 | pass |
