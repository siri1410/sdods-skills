# SDODS skills and Claude Code plugin

Skills, subagents and the MCP server that let AI coding agents write, run, heal and review
[SDODS](https://sdods.com) tests — BDD automation for UI, API and hybrid flows.

SDODS is free: Apache-2.0 on npm (`@sdods/cli`), unlimited API tokens, no paid tier.

> Generated from the SDODS monorepo by `scripts/build-agent-plugin.ts` (version 0.7.0).
> Changes made directly in this repository are overwritten on the next release.

## Claude Code plugin

Skills, the five SDODS subagents, the MCP server, slash commands and a session hook, in one install:

```text
/plugin marketplace add siri1410/sdods-skills
```

```text
/plugin install sdods@sdods
```

Commands: `/sdods:generate`, `/sdods:heal`, `/sdods:plan`, `/sdods:review`, `/sdods:setup`, `/sdods:test`, `/sdods:upgrade`.

To offer it to everyone who opens a repository, commit this to `.claude/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "sdods": { "source": { "source": "github", "repo": "siri1410/sdods-skills" } }
  },
  "enabledPlugins": { "sdods@sdods": true }
}
```

## Any agent: skills with npx

Works with Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, OpenCode, Amp, Goose and more:

```bash
npx skills add siri1410/sdods-skills
```

Or with the SDODS CLI, which needs no GitHub access:

```bash
npx -y @sdods/cli skills install
```

| Skill | What it does |
| --- | --- |
| `sdods` | Work in an SDODS test-automation workspace — BDD features for UI, API and hybrid flows. Use when writing, fixing or reviewing Gherkin features, steps, page objects or project/env YAML, running suites, reading results, or using the sdods CLI or its MCP tools. |
| `sdods-record` | Record a browser flow with SDODS for a given project, environment, user role and device, save it as a runnable spec, replay it, and optionally convert it into a Gherkin feature with reusable steps. Use when the user says "record", "codegen", "capture a flow", "re-record as <role>", or wants the same flow recorded across environments or users. |
| `sdods-run` | Run SDODS test suites for a project across environments, layers (ui/api/hybrid/recorded), browsers, suites (@smoke/@regression) and user roles, then read the results. Use when the user says "run the tests", "smoke on staging", "regression on all browsers", "run as <role>", or asks what failed. |
| `sdods-start-ui` | Start the SDODS web UI on any OS and get the first user signed in. Use when someone says "start the UI", "open the dashboard", "run the web app", "sdods serve", "I can't log in", "it says the web UI is not available", "port 4444 in use", "how do I register", or is onboarding onto SDODS for the first time. |

## MCP server only

```bash
claude mcp add sdods -- npx -y @sdods/cli mcp
```

Every other client — Codex, Cursor, VS Code, Windsurf, Gemini CLI, Zed, JetBrains, Claude Desktop
and a shared team endpoint — is covered in the
[AI coding tools guide](https://docs.sdods.com/docs/guides/ai-coding-tools/).

## License

Apache-2.0.
