# Bolt Documentation

Documentation for [Bolt](https://github.com/bolt-builder/bolt-cli), the AI coding agent built for the terminal. Built with [Mintlify](https://mintlify.com); pages are MDX files and navigation lives in `docs.json`.

## Structure

- `index.mdx`, `installation.mdx`, `quickstart.mdx` — getting started
- `concepts/` — core concepts (agents, sessions, permissions, config, and more)
- `tui/` — terminal UI guides
- `extending/` — plugins, custom commands, skills, MCP
- `server/` — headless server and automation
- `desktop/` — desktop app
- `reference/` — command reference (generated from the CLI's `--help` output), scripting and CI guide, configuration schema, environment variables, troubleshooting
- `changelog/` — release notes
- Two-letter directories (`de/`, `ja/`, `zh/`, ...) — translated trees; edit English pages first, translations follow separately

## Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mint) and run a local preview from the repo root (where `docs.json` is located):

```bash
npm i -g mint
mint dev
```

View the preview at `http://localhost:3000`.

Before pushing, check for broken links:

```bash
npx mintlify broken-links
```

## Contributing

- English content is the source of truth. Do not hand-edit translated trees.
- `reference/commands.mdx` is generated from bolt-cli's `--help` output via `script/docs-reference.ts` in the [bolt-cli repo](https://github.com/bolt-builder/bolt-cli); regenerate rather than editing by hand.
- Changes merged to `main` deploy to production automatically.

## Troubleshooting

- If the local preview isn't running, run `mint update` to get the latest CLI.
- If a page loads as a 404, make sure you are running in the folder containing `docs.json`.
