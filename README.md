# AI Development Environment — Documentation

The [Mintlify](https://mintlify.com) documentation site for [AI Development Environment](https://github.com/bludesign/ai-development-environment), a self-hosted control plane for AI-assisted development across your machines.

## Structure

| Path | Contents |
| --- | --- |
| `docs.json` | Site config: theme, colors, navigation, navbar, footer |
| `index.mdx`, `quickstart.mdx` | Getting started |
| `dashboard.mdx`, `notifications.mdx` | Top-level dashboard pages |
| `agents/`, `workflows/`, `commands/`, `codebases/`, `worktrees/`, `builds/` | Dashboard areas |
| `ai/`, `skills/` | Plans, Sessions, drafts, usage, costs, and skill packages |
| `debugging/`, `github/`, `jira/`, `system/` | Debugging tools and integrations |
| `reference/` | Local development, APIs, database, and hosting |
| `images/light/`, `images/dark/` | Page screenshots, one pair per documented page |
| `logo/`, `favicon.svg` | Branding |

Every page is an MDX file with YAML frontmatter (`title`, `description`). Pages are only routable once they are listed in the `navigation` block of `docs.json`.

## Local preview

Install the Mintlify CLI and run it from the repository root, where `docs.json` lives:

```bash
npm i -g mint
```

```bash
mint dev
```

The preview is served at `http://localhost:3000`.

> **Name collision:** Mintlify's CLI binary is `mint`, the same name as the Swift package manager installed by `brew install mint`. If `mint dev` prints Swift Package Manager usage, the wrong binary is first on your `PATH`. Check with `which -a mint` and call the npm one by its full path, or uninstall the Homebrew package.

Useful checks:

```bash
mint broken-links
```

```bash
mint update
```

## Adding a page

1. Create the MDX file in the matching directory, with `title` and `description` frontmatter.
2. Add screenshots to `images/light/` and `images/dark/` using the page's file name, then open the page with a `<Frame>` holding both images — `className="block dark:hidden"` for light and `className="hidden dark:block"` for dark. See [`worktrees/worktrees.mdx`](worktrees/worktrees.mdx) for the pattern.
3. Register the page path (no extension) under the right group in `docs.json`.
4. Run `mint dev` and confirm the page renders and appears in the sidebar.

Screenshots come from the application repository: `npm run screenshots` captures every route against seeded mock data at four viewport and color-scheme combinations, writing PNGs to `screenshots/<project>/`. `npm run screenshots:copy` then publishes the desktop captures into `images/light/` and `images/dark/` here. See [Local development](reference/development.mdx) for the full pipeline.

## Writing style

House rules also live in [`AGENTS.md`](AGENTS.md) for AI coding tools:

- Active voice, second person ("you").
- One idea per sentence; sentence case for headings.
- Bold for UI elements — click **Settings**.
- Code formatting for file names, commands, paths, and code references.
- Each page opens with its screenshot frame, then a one-paragraph summary, then **Using the page** and **Notes** sections.

## Publishing

Changes to the default branch deploy automatically once Mintlify's GitHub app is installed from the [Mintlify dashboard](https://dashboard.mintlify.com/settings/organization/github-app).

## License

MIT. See [`LICENSE.md`](LICENSE.md).
