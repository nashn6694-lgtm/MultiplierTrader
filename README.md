# Multiplier Auto-Trader — Vercel

Website conversion of `AccuEUR.py` using the OAuth 2.0 + PKCE login flow from the supplied Vercel source.

## Features
- Deriv OAuth 2.0 / PKCE login (primary browser login).
- Optional PAT login retained from the source project.
- MULTUP / MULTDOWN multiplier contracts.
- Multiplier 1 or 40.
- USD/EUR proposal currency selector.
- Manual stake or full-balance auto-stake.
- Fixed tick interval auto-trading.
- Tick-based take-profit and contract monitoring.
- Last 8 trades, wins/losses, running P/L and live tick log.
- Admin-protected markup statistics via `/api/markup`.

## OAuth setup
1. Deploy on a stable HTTPS domain.
2. Register the exact callback `https://YOUR-DOMAIN/callback` in the Deriv OAuth application.
3. The OAuth app ID is `34B2jcoodqOXrLQgcvib9` from the supplied source.
4. The site uses PKCE S256 and validates the OAuth `state` value in same-origin session storage.
5. OAuth tokens are kept in browser local storage for session restoration; the PAT field is never populated by OAuth.

## Vercel environment variables
- `MARKUP_PAT_TOKEN`
- `MARKUP_ADMIN_PASSWORD`

`DERIV_APP_ID` may be kept for deployment documentation, but the browser build uses the source project's explicit PAT and OAuth app IDs.

## Important
This is live trading software. Test with a demo account or very small amounts first. Never commit PATs, OAuth tokens, or markup credentials.
