# Bialet Web Developer

A **Bialet** development skill that follows the classic PHP workflow:  
design the static page first, iterate until it feels right, then make it dynamic one step at a time.

You don’t need to be an expert programmer – the assistant will explain every decision and never jump ahead without your confirmation.

---

## What this skill does

- Guides you through building a complete Bialet application in four clear phases:
  1. **Static HTML & visual structure** – pure HTML with placeholder data.
  2. **Identify dynamic parts & design the database** – create SQLite tables.
  3. **Add server‑side logic** – replace placeholders with real data and form handling.
  4. **Polish & edge cases** – validation, error states, and optional HTMX.

- Embeds all the official Bialet best practices:
  - File‑based routing (no `routes/` folder)
  - Direct SQL with parameterised queries (no ORM)
  - Semantic HTML + PicoCSS for class‑less styling
  - Server‑side rendering, full page reloads by default
  - Minimal, readable Wren code with implicit returns

---

## How to use

1. Add this skill to your AI assistant (GPT, Claude, etc.).
2. Tell it what you want to build, for example:  
   *“I want a simple guestbook where people can leave messages.”*
3. The assistant will start Phase 1 – showing you a fully static version of your page.
4. Only after you’re happy with the design will it move on to databases and dynamic code.
5. By the end, you’ll have a working Bialet app, ready to run.

---

## Example conversation snippet

**User:** *I want to build a blog.*  
**Assistant:** *Great! Let’s start with the static HTML. Here’s your homepage with two fake posts…*  
(Assistant shows `index.wren` and `_app/template.wren`)

**User:** *Looks perfect – can we make the posts real?*  
**Assistant:** *Absolutely. First, let’s design the `posts` table. Here’s the migration file…*  
(Assistant writes `_app/migration.wren`)

**User:** *Yes, that’s all I need.*  
**Assistant:** *Now I’ll add a `Post` model and update the page to fetch real data.*  
(Assistant writes `_app/domain.wren` and updates `index.wren`)

… and so on, always asking for your approval before proceeding.

---

## Requirements

- This skill works with any AI assistant that supports prompt‑based skills (ChatGPT, skills.sh, etc.).
- No prior knowledge of Bialet or Wren is required – the assistant teaches you as you build.

---

## Philosophy

> “Start with the page, not the database.”

Bialet applications are meant to feel like the early web: you make a simple page, test it, then add the bits that need to be dynamic. There’s no bundler, no configuration, no magic. This skill enforces that **iterative mindset** so even beginners can build real apps with confidence.

---

## Tags

`Bialet` `Wren` `SQLite` `server-rendered` `beginner-friendly` `HTML-first` `web-framework`

---

**Happy building!**
