# Connect Vault Station HQ to pump.fun

This file is the operator checklist. Do it once, in this order.

## Why this GitHub account

pump.fun can route creator fees to a **GitHub user**.

| Requirement | Station status |
| --- | --- |
| Recipient must be a GitHub **user**, not an org | `VaultedLabs` is a user |
| Numeric user ID | `328830813` |
| Claim happens only inside pump.fun web or the pump.fun app | Log in with this same GitHub account |
| Fee split, once set, is locked | Do not submit until the mint and shares are final |

Source: pump.fun public docs / `@pump-fun/pump-sdk` GitHub recipient checklist.

## Fields to paste on the coin

| pump.fun field | Paste this |
| --- | --- |
| Website | `https://vaultedlabs.github.io/vault-station-hq/` |
| GitHub | `https://github.com/VaultedLabs/vault-station-hq` |
| Twitter / X | `https://x.com/VaultStationHQ` |

## Paste-ready coin description

```
Vault Station HQ
Observing what launches, what survives, and what the data says.
Experiments conducted onchain.

Official record:
https://github.com/VaultedLabs/vault-station-hq

Landing:
https://vaultedlabs.github.io/vault-station-hq/

X: @VaultStationHQ
GitHub user: VaultedLabs (328830813)

◉ VAULT STATION
```

Keep the description short. pump.fun truncates.

## After the mint exists

1. Put the mint into [`official.json`](./official.json) under `token.mint`.
2. Put the coin URL into `token.pumpfun_url` as `https://pump.fun/coin/<MINT>`.
3. Put name and ticker only if they are the issued names.
4. Update the landing page contract strip.
5. Announce from [@VaultStationHQ](https://x.com/VaultStationHQ) with the mint written in full. Close with `◉ VAULT STATION`.

Until those fields are filled, the Station has no contract. Treat any other mint as noise.

## Fee routing (optional, irreversible)

If the coin should pay this GitHub user:

1. Initialize the social fee PDA for user id `328830813` / platform GitHub (the official SDK helpers do this).
2. Add shareholder `{ userId: "328830813", platform: GitHub, shareBps: <your split> }`.
3. Remaining bps go to wallet shareholders. Total must be 10_000.
4. Submit once. Do not experiment on mainnet with the live mint.

Claim path: open the coin on pump.fun → log in with GitHub as `VaultedLabs` → claim. There is no off-platform claim flow.

## Enable the public landing

GitHub Actions cannot create a Pages site on this account (`Resource not accessible by integration`). Enable it once in the UI:

1. Open https://github.com/VaultedLabs/vault-station-hq/settings/pages
2. Under **Build and deployment** → **Source**, choose **Deploy from a branch**
3. Branch: `main` · folder: `/ (root)`
4. Save
5. Wait about a minute, then open https://vaultedlabs.github.io/vault-station-hq/
