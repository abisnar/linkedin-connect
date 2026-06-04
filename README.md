# linkedin-connect

The hosted **"Connect LinkedIn to Claude"** login page for [linkedin-mcp](https://github.com/abisnar/linkedin-mcp).

🔗 **https://abisnar.github.io/linkedin-connect/**

It's a single static page that holds **no secrets**. It starts LinkedIn's official OAuth flow and shows you the one-time authorization code, which Claude then exchanges locally via the linkedin-mcp `complete_auth` tool (your client secret never leaves your machine).

## Use it

1. In your [LinkedIn app](https://www.linkedin.com/developers/apps), add `https://abisnar.github.io/linkedin-connect/` as an **Authorized redirect URL**.
2. Open the page, enter your **Client ID**, and click **Sign in with LinkedIn**.
3. Copy the code it shows you and paste the suggested prompt to Claude. It runs `complete_auth` and saves your token.

The page reads its redirect URI from the browser's location, so the same file works locally (`npm run login` in linkedin-mcp) or on any HTTPS host.

> Source of truth is `docs/index.html` in [linkedin-mcp](https://github.com/abisnar/linkedin-mcp); this repo just hosts it on GitHub Pages.
