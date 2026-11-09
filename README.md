# 🚲 Bialet Web Developer

<p align="center">
  <strong>Small on purpose. Taught step by step.</strong><br />
  A Bialet development skill that follows the classic PHP workflow.
</p>

<p align="center">
  Design the static page first, iterate until it feels right, then make it<br />
  dynamic one step at a time — with an assistant that explains every decision<br />
  and never jumps ahead without your confirmation.
</p>

<p align="center">
  <a href="https://bialet.dev">
    <img src="https://img.shields.io/badge/docs-bialet.dev-7c3aed.svg" alt="Docs">
  </a>
  <a href="https://github.com/bialet/skills/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License">
  </a>
</p>

## What is Bialet?

Bialet is a single-binary web framework: an HTTP server, SQLite, and the
object-oriented [Wren language](https://wren.io) in one executable. You build
data-driven apps from `.wren` files — no package manager, no YAML, no separate
database server, no build step. The Linux x86_64 binary is 3.7 MB.

Routes follow the filesystem: each `.wren` file is a handler that returns an
HTML page, so an app is a handful of files and the filename is the URL. Bialet
has been in development since 2023 and runs in production at
[home.dev.ar](https://home.dev.ar).

## Install Bialet

Prebuilt binaries and an install script are available for macOS ARM,
Ubuntu x86_64, and Ubuntu ARM64:

```bash
curl -fsSL https://get.bialet.dev | sh
```

Other options: [Homebrew, Docker, and release
archives](https://bialet.dev/installation.html). On Windows, download the
`.zip` from the [latest
release](https://github.com/bialet/bialet/releases/latest).

## What this skill does

It guides you through building a complete Bialet application in four clear
phases, confirming each one before moving on:

| Phase | What happens |
| --- | --- |
| **1. Static HTML & visual structure** | Pure HTML with placeholder data, styled with a classless CSS framework (the examples use PicoCSS). |
| **2. Database design** | The placeholders become a `_app/migration.wren` with SQLite tables, keys and timestamps. |
| **3. Server-side logic** | A small domain class, parameterised SQL, form handling, and the real data in the page. |
| **4. Polish & edge cases** | Validation, empty states, 404s, and optionally HTMX for the one interaction that needs it. |

It embeds the framework's conventions so the assistant writes idiomatic Wren
from the first file:

- **File-based routing** — the filesystem *is* the router; there is no
  `routes/` folder.
- **Direct SQL** with `?` placeholders — no ORM, no string concatenation.
- **Semantic HTML** and server-rendered pages; full reloads by default.
- **Small, readable Wren** — single-expression methods return implicitly, and
  logic lives at the top of the file with the view at the bottom.

## How to use it

1. Add this skill to your AI assistant (Claude, ChatGPT, Cursor, or any client
   that loads `SKILL.md` files).
2. Install Bialet and check it runs:

   ```bash
   bialet -r 'System.log("Hello, World!")'
   ```

3. Tell the assistant what you want to build, for example:
   *"I want a simple guestbook where people can leave messages."*
4. It starts with Phase 1 — a fully static version of your page.
5. Only after you are happy with the design does it move on to the database
   and the dynamic code.

By the end you have a running Bialet app and a project structure you can keep
growing.

### Example conversation

**User:** *I want to build a blog.*
**Assistant:** *Great! Let's start with the static HTML. Here's your homepage
with two fake posts…*
(Assistant shows `index.wren` and `_app/template.wren`)

**User:** *Looks perfect — can we make the posts real?*
**Assistant:** *Absolutely. First, let's design the `posts` table. Here's the
migration file…*
(Assistant writes `_app/migration.wren`)

**User:** *Yes, that's all I need.*
**Assistant:** *Now I'll add a `Post` model and update the page to fetch real
data.*
(Assistant writes `_app/domain.wren` and updates `index.wren`)

…and so on, always asking for approval before the next phase.

## What the assistant will not do

- Create a `routes/`, `validators/` or `static/` folder — the file layout is
  the routing.
- Add a bundler, a package manager or a config file.
- Reach for JavaScript before plain HTML and SQL have been tried.
- Concatenate user input into SQL.

## When Bialet fits — and when it does not

The same limits the framework documents apply to the apps this skill builds:

- **One worker per process, with instant queueing.** Requests are served
  sequentially per worker; for parallel concurrency on multi-core servers, run
  several local instances behind Caddy or nginx. See
  [Deployment](https://bialet.dev/deployment.html).
- **HTTP/1.0, no native TLS.** Put nginx, Apache, or Caddy in front for HTTPS,
  HTTP/2, rate limiting, and request buffering.
- **SQLite is the database.** One file (`_db.sqlite3` by default), no external
  database server. WAL mode is available with `-w`.
- **Wren only.** Syntax highlighting is available; there is no LSP.
- **No package registry.** External modules are imported from GitHub paths.
- **No WebSockets.** Request/response HTTP only; use polling for realtime.

If the project needs horizontal scaling across machines, a mature package
ecosystem, or a single-page app, this skill is the wrong tool.

## Learn more

- [Documentation](https://bialet.dev) — the complete manual.
- [Quick start: a guestbook](https://bialet.dev/quickstart.html) — the same
  three-file app this skill builds.
- [Common Pitfalls](https://bialet.dev/pitfalls.html) — the traps inline HTML
  and Wren spring on you (also summarised in `SKILL.md`).
- [Recipes](https://bialet.dev/recipes.html) — dates, money in cents, CSV
  exports, `Util`/`Config`, and test hygiene.
- [llms.txt](https://bialet.dev/llms.txt) — a machine-readable index of every
  page, for the assistant.

## Requirements

- Bialet installed and on the `PATH`.
- Any AI assistant that supports prompt-based skills (Claude, ChatGPT,
  skills.sh, …).
- No prior knowledge of Bialet or Wren — the assistant teaches you as you
  build.

## Philosophy

> "Start with the page, not the database."

Bialet applications are meant to feel like the early web: you make a simple
page, test it, then add the bits that need to be dynamic. There's no bundler,
no configuration, no magic. This skill enforces that **iterative mindset** so
even beginners can build real apps with confidence.

## Tags

`Bialet` `Wren` `SQLite` `server-rendered` `beginner-friendly` `HTML-first` `web-framework`

---

**Happy building!**
