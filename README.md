<div align="center">

<img src="assets/cover.png" alt="Adapty through HeyMetra's MCP server" width="100%">

# Adapty &times; HeyMetra

**Subscription revenue, MRR, trials and refunds over any range.**

Your subscription revenue lives in Adapty. What you paid to get those subscribers does not. Ask about both in the same sentence.

[![MCP Registry](https://img.shields.io/badge/MCP_Registry-com.heymetra%2Fheymetra-1f6feb)](https://registry.modelcontextprotocol.io/v0/servers/com.heymetra%2Fheymetra/versions)
[![Transport](https://img.shields.io/badge/transport-Streamable_HTTP-444)](https://modelcontextprotocol.io/)
[![Auth](https://img.shields.io/badge/auth-OAuth_2.1-444)](https://heymetra.com/security/)
[![Connector page](https://img.shields.io/badge/heymetra.com-adapty-1f6feb)](https://heymetra.com/connectors/adapty/)

```
https://mcp.heymetra.com/mcp
```

</div>

---

## Ask it things like

> How did subscription revenue move day by day this month?

> How many trials started last month, and how many expired?

> How much came back as refunds last month?

> What are revenue, MRR, active subscriptions and new trials this month?

> Which of my apps is making the most MRR?

No dashboard, no export, no query language. You ask in the assistant you already use and the answer comes back with the account it came from.

## Connect Adapty

**1. Open the app you want to read**

Sign in at app.adapty.io and pick the app from the switcher at the top. An Adapty key belongs to ONE app, so the app you are looking at now is the app this connection will answer for.

> A portfolio is one connection per app, not one for the account. Five apps means doing this five times, and each connection gets its own name here — which is what you will call it when you ask a question about it.

**2. Go to App settings → General and find Api keys**

It is at app.adapty.io/settings/general. Scroll to the section headed Api keys; it lists a Public SDK Key and a Secret Key together.

> Adapty's own pages call this screen both 'App settings → General' and 'Settings → General'. They are the same screen.

**3. Copy the Secret Key**

The one that starts with secret_live_. Not the one that starts with public_live_ — that is the Public SDK Key, it belongs inside your app, and it cannot read any of these figures.

> If you paste the public one HeyMetra will say so by name rather than letting Adapty answer with a bare login error.

**4. Paste it into HeyMetra and give the connection a name**

On the Connections screen choose Adapty, paste the key, and name it after the app — 'Cleanr', not 'Adapty'. The key goes to the vault and is never shown again; HeyMetra proves it works before saving anything, so a rejected key never leaves a connection that looks healthy.

**5. Add HeyMetra to the assistant you use**

Claude, ChatGPT, Cursor or Codex, with the details HeyMetra gives you. The Adapty tools appear there once the connection is saved.

Watch what you paste:

- Anything starting `public_live_` is **the Public SDK Key, which belongs in your app** and will be refused by name.

## Then add HeyMetra to your assistant

Add HeyMetra once and it is there in every conversation. The address is the same everywhere:

```
https://mcp.heymetra.com/mcp
```

### One command

```bash
npx add-mcp https://mcp.heymetra.com/mcp
```

[`add-mcp`](https://www.npmjs.com/package/add-mcp) is a third-party installer that writes the configuration for Claude Code, Codex, Cursor, Antigravity, VS Code and seventeen other agents. It infers the name from the address, so the server lands as `heymetra`. Run against this endpoint before it was written here.

### Or by hand

<details>
<summary><b>Claude</b> — Settings → Customize → Connectors → Add custom connector</summary>

Paste the address above into Settings → Customize → Connectors → Add custom connector.

_On Team and Enterprise plans only an owner can add it, under Organization settings._

Full walkthrough: [heymetra.com/mcp/claude/](https://heymetra.com/mcp/claude/)
</details>

<details>
<summary><b>ChatGPT</b> — Settings → Security and login → Developer mode, then chatgpt.com/plugins</summary>

Paste the address above into Settings → Security and login → Developer mode, then chatgpt.com/plugins.

_The endpoint has to include its /mcp path here._

Full walkthrough: [heymetra.com/mcp/chatgpt/](https://heymetra.com/mcp/chatgpt/)
</details>

<details>
<summary><b>Grok</b> — grok.com/connectors → New Connector → Custom</summary>

Paste the address above into grok.com/connectors → New Connector → Custom.

_XAI calls this “bring your own MCP”._

Full walkthrough: [heymetra.com/mcp/grok/](https://heymetra.com/mcp/grok/)
</details>

<details>
<summary><b>Perplexity</b> — Settings → Connectors → Custom connector → Remote</summary>

Paste the address above into Settings → Connectors → Custom connector → Remote.

_Perplexity documents it as a Pro, Max and Enterprise feature._

Full walkthrough: [heymetra.com/mcp/perplexity/](https://heymetra.com/mcp/perplexity/)
</details>

<details>
<summary><b>Claude Code</b> — claude mcp add --transport http</summary>

```bash
claude mcp add --transport http heymetra https://mcp.heymetra.com/mcp
```

_Or a .mcp.json in the project root; /mcp inside a session shows what connected._

Full walkthrough: [heymetra.com/mcp/claude-code/](https://heymetra.com/mcp/claude-code/)
</details>

<details>
<summary><b>Codex</b> — ~/.codex/config.toml</summary>

```toml
[mcp_servers.heymetra]
url = "https://mcp.heymetra.com/mcp"
```

_Under an [mcp_servers.<name>] section, then codex mcp login._

Full walkthrough: [heymetra.com/mcp/codex/](https://heymetra.com/mcp/codex/)
</details>

<details>
<summary><b>Cursor</b> — ~/.cursor/mcp.json, or .cursor/mcp.json in a project</summary>

```json
{
  "mcpServers": {
    "heymetra": { "url": "https://mcp.heymetra.com/mcp" }
  }
}
```

_Leave the static OAuth fields empty — they exist for servers that cannot register themselves._

Full walkthrough: [heymetra.com/mcp/cursor/](https://heymetra.com/mcp/cursor/)
</details>

<details>
<summary><b>Antigravity</b> — ~/.gemini/config/mcp_config.json, or .agents/mcp_config.json in a project</summary>

```json
{
  "mcpServers": {
    "heymetra": { "serverUrl": "https://mcp.heymetra.com/mcp" }
  }
}
```

_The key is serverUrl, not url — the one every other JSON client spells differently._

Full walkthrough: [heymetra.com/mcp/antigravity/](https://heymetra.com/mcp/antigravity/)
</details>

## What it may and may not touch

Propose a change through this account's own API, for operations HeyMetra does not cover. Nothing is sent until you approve it, and HeyMetra cannot undo it afterwards.

Permissions are switched on per connection, and one you leave off is a tool your assistant never sees.

| Permission | What it covers | Changes anything? |
|---|---|---|
| **Direct API access** | Let your assistant use this account's own API for anything HeyMetra's other operations do not cover. It reads directly, and what comes back is the provider's own answer rather than a figure HeyMetra has checked. It can also propose changes — those are never applied until you approve them, and HeyMetra cannot undo one afterwards. | Yes — every change waits for your approval |

<details>
<summary>What each permission lets an assistant do, in full</summary>

- Ask this account's own API a question HeyMetra's other operations do not cover. Reads only, and the answer is the provider's own rather than a figure HeyMetra has checked.
- Propose a change through this account's own API, for operations HeyMetra does not cover. Nothing is sent until you approve it, and HeyMetra cannot undo it afterwards.
</details>

Anything that would change something comes back as a proposal you approve, inside bounds that live in code rather than in a prompt: ±50% on a budget, 5 campaigns per action and 20 changes a rolling day, and an approval that expires after 30 minutes. [How that works](https://heymetra.com/security/).

## When something goes wrong

<details>
<summary>The key is rejected and it was copied straight from the Api keys screen.</summary>

**Why:** Two keys sit on that screen and only the Secret Key reads analytics. The Public SDK Key is for the app itself.

**Fix:** Check what you pasted starts with secret_live_ rather than public_live_, and copy the other one.

</details>

<details>
<summary>A connection that worked for months suddenly answers with a login error.</summary>

**Why:** Somebody generated a new key in Adapty and deleted the old one. Generating alone does not break anything — pressing the trash icon beside the previous key does.

**Fix:** Copy the current Secret Key from App settings → General and paste it into this connection with the pencil. The connection keeps its name and everything pointing at it.

</details>

<details>
<summary>You have a token from 'adapty auth login' and it is not accepted.</summary>

**Why:** That is the Developer CLI token, from Settings → Developer API. It authorises the command-line tool and nothing else.

**Fix:** Use the Secret Key from App settings → General instead — it starts with secret_live_ and is copied, not issued by a login flow.

</details>

<details>
<summary>Revenue and MRR answer, but proceeds and net revenue come back as 'not reported for this app'.</summary>

**Why:** Those two need store payment data, and Adapty only has it once App Store Connect or Google Play reporting is wired into that app. Until then Adapty has no figure to give, so HeyMetra says so rather than showing revenue in their place.

**Fix:** Connect the store's reporting in Adapty. Everything that does not depend on it keeps answering in the meantime.

</details>

<details>
<summary>Answers come back slowly, or one in a batch fails.</summary>

**Why:** Adapty's analytics API allows two requests a second per key, and a question that spans several charts or several apps makes one call each.

**Fix:** Ask again — HeyMetra reports a rate limit as a temporary gap rather than as no data, so the figure is not quietly replaced by a zero.

</details>

## What HeyMetra reads from Adapty

Connect with each app's secret key — an Adapty key belongs to one app, so a portfolio is one connection per app — and your MCP client gets one tool that composes Adapty's analytics: revenue, proceeds, net revenue, MRR, ARR, ARPU, ARPPU, subscription and trial counts by lifecycle event, refunds and installs, each as a total plus a day-by-day series. The same call filters by store, so an app that ships on both can be asked about the App Store and Google Play separately instead of only about the two added together. Paywall and A/B figures are not among the metrics this connector reads today. Revenue is dated by transaction and sits before the store's fee, so an answer states which basis it used rather than letting you compare it with cohort-based ad figures by accident. An Adapty secret key cannot be split into a read half and a write half, so HeyMetra asks you at connect time whether this connection may change anything.

<details>
<summary>About Adapty</summary>

Adapty runs mobile in-app subscriptions and paywall analytics — revenue, conversion, retention, and paywall A/B tests across iOS and Android. It’s where subscription growth and paywall performance are measured.
</details>

## One connection, not seven

The reason to read Adapty through HeyMetra rather than through a server that only knows Adapty is everything else it can answer in the same breath:

**Ads** — [Google Ads](https://heymetra.com/connectors/google-ads/) · [Meta](https://heymetra.com/connectors/meta-ads/)

**Analytics** — [Google Analytics 4](https://heymetra.com/connectors/google-analytics-4/) · [Google Search Console](https://github.com/zeisoft/google-search-console-mcp) · [PostHog](https://github.com/zeisoft/posthog-mcp)

**Ecommerce** — [Shopify](https://heymetra.com/connectors/shopify/) · [Trendyol](https://github.com/zeisoft/trendyol-mcp) · [WooCommerce](https://github.com/zeisoft/woocommerce-mcp)

**Revenue & CRM** — [Stripe](https://heymetra.com/connectors/stripe/) · [HubSpot](https://heymetra.com/connectors/hubspot/) · [Zoho CRM](https://github.com/zeisoft/zoho-crm-mcp) · [Zoho SalesIQ](https://github.com/zeisoft/zoho-salesiq-mcp) · [Zoho Marketing Automation](https://github.com/zeisoft/zoho-marketing-automation-mcp)

**Mobile** — [AppsFlyer](https://github.com/zeisoft/appsflyer-mcp) · [RevenueCat](https://heymetra.com/connectors/revenuecat/) · **Adapty** · [App Store Connect](https://github.com/zeisoft/app-store-connect-mcp)

**Work** — [Google Calendar](https://heymetra.com/connectors/google-calendar/) · [Google Meet](https://heymetra.com/connectors/google-meet/) · [Jira](https://github.com/zeisoft/jira-mcp)

**Channels** — [Slack](https://github.com/zeisoft/slack-mcp) · [Telegram](https://github.com/zeisoft/telegram-mcp)

The full catalogue is at [heymetra.com/connectors/](https://heymetra.com/connectors/).

## Links

- [Adapty connector page](https://heymetra.com/connectors/adapty/)
- [HeyMetra](https://heymetra.com/) — what the product is
- [Setup for every assistant](https://heymetra.com/mcp/)
- [Security and limits](https://heymetra.com/security/)
- [Pricing](https://heymetra.com/pricing/)
- [HeyMetra's own repository](https://github.com/zeisoft/heymetra-mcp)

---

<sub>Built by <a href="https://zeisoft.com">Zeisoft</a>, who make HeyMetra. Not affiliated with Adapty. This README is generated from HeyMetra's live connector catalogue and refreshed daily; corrections are welcome as issues.</sub>
