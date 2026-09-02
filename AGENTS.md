# AI Development Environment documentation instructions

## Product and audience

- This is the Mintlify documentation for AI Development Environment, a self-hosted control plane for AI-assisted development across managed machines.
- Write for operators and developers who install the control plane, connect agents, use the web and iOS apps, or automate it through GraphQL, MCP, and workflows.
- Document shipped behavior from the application repositories. Do not invent configuration, routes, limits, or security guarantees.

## Mintlify workflow

- Pages are MDX files with YAML `title` and `description` frontmatter.
- Register every routable page in `docs.json`; a file alone does not appear in navigation.
- Reuse Mintlify components already present in this repository, including `Frame`, `Note`, `Tip`, `Warning`, `Card`, `Columns`, and tables.
- For a page backed by a web route, open with the matching light and dark desktop screenshots. Use `className="block dark:hidden"` and `className="hidden dark:block"` inside `Frame`.
- Application screenshots and `schema.graphql` are generated in the web repository. Run its VS Code tasks in this order: `screenshots`, `screenshots:copy`, `schema:copy`, then `schema:publish`.
- Validate with `mint broken-links`. Preview with the npm Mintlify CLI from the repository root when visual review is needed.

## Terminology and scope

- Use **AI Development Environment** for the product and **control plane** for the web server.
- Use **agent** for the software installed on a managed machine and **endpoint** for an HTTP or SSE route.
- Use **plan** and **session** for model runs. Use **workflow** for the product’s event/action automation.
- Cover the web and native iOS management experiences when both expose a feature.
- Include security and retention implications wherever a feature stores credentials, headers, bodies, logs, or other sensitive data.

## Style

- Use active voice and second person.
- Keep sentences concise and headings in sentence case.
- Bold UI labels, and use code formatting for commands, routes, field names, files, GraphQL operations, MCP tools, and workflow kinds.
- Prefer exact examples and tables over vague summaries.
- Link related product pages with root-relative documentation links.

## Page structure

- Begin route-backed pages with the light/dark screenshot frame.
- Follow with a short explanation of the page and its route.
- Use task-oriented sections that explain how to operate the feature, its defaults and limits, and failure behavior.
- End with related pages when useful.
