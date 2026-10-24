---
marp: true
theme: default
paginate: true
size: 16:9
style: |
  section {
    background: #101827;
    color: #edf3fa;
    font-family: Inter, "Segoe UI", Arial, sans-serif;
    font-size: 25px;
    padding: 52px 68px;
    justify-content: center;
  }

  h1, h2 {
    color: #f7fbff;
    font-family: Anton, Impact, "Arial Narrow", sans-serif;
    font-weight: 400;
    letter-spacing: 0.2px;
    line-height: 1;
    margin: 0 0 26px;
  }

  h1 { font-size: 88px; }
  h2 { font-size: 60px; }

  h3 {
    color: #56d6c2;
    font-size: 27px;
    margin: 0 0 12px;
  }

  p { margin: 0 0 14px; }

  ul, ol {
    font-size: 27px;
    line-height: 1.35;
  }

  li { margin: 0 0 11px; }

  strong { color: #56d6c2; }

  code {
    background: rgba(86, 214, 194, 0.14);
    border-radius: 5px;
    color: #b9fff2;
    padding: 2px 7px;
  }

  pre {
    background: #0a111d;
    border: 1px solid #2a3b50;
    border-radius: 10px;
    font-size: 19px;
    line-height: 1.35;
    padding: 18px 22px;
  }

  section.light {
    background: #f3f6fa;
    color: #172337;
  }

  section.light h1,
  section.light h2 { color: #172337; }

  section.light h3,
  section.light strong { color: #087f73; }

  section.light code {
    background: #dceeea;
    color: #075e56;
  }

  section.light pre {
    background: #e8edf3;
    border-color: #d0d9e4;
    color: #172337;
  }

  section.title {
    background: #101827;
    justify-content: center;
    overflow: hidden;
  }

  section.title::before {
    color: rgba(86, 214, 194, 0.09);
    content: "DEV";
    font-family: Anton, Impact, sans-serif;
    font-size: 300px;
    line-height: 0.8;
    position: absolute;
    right: 26px;
    bottom: 24px;
  }

  section.title h1 {
    font-size: 112px;
    max-width: 780px;
    position: relative;
    z-index: 1;
  }

  .eyebrow {
    color: #56d6c2;
    font-size: 18px;
    font-weight: 700;
    letter-spacing: 3px;
    margin-bottom: 22px;
    text-transform: uppercase;
  }

  .small {
    font-size: 20px;
    line-height: 1.35;
  }

  .callout {
    border-left: 5px solid #56d6c2;
    font-size: 24px;
    margin-top: 22px;
    padding: 10px 0 10px 18px;
  }
---

<!-- _class: title -->

# Development<br>Environment

---

<!-- _class: light -->

## Lab Plan

1. Introduction
2. Problems Encountered
3. Solutions Implemented

---

<div class="eyebrow">01 / Introduction</div>

## A Workspace That Works

This lab improves the everyday development workflow in **Visual Studio Code**: make project files discoverable, keep code reminders visible, and preview web pages and presentations without leaving the editor.

### Concepts & tools

- Explorer visibility and workspace settings
- Todo Highlight, Live Server, and Marp
- IDE: editor, extensions, terminal, and preview tools

---

<!-- _class: light -->

<div class="eyebrow">02 / Problems Encountered</div>

## Small Friction, Repeated Often

- Hidden files and folders—especially `.git`—were not visible in the Explorer.
- `README.md` was missing from the file list.
- Reminders about code that needed attention were easy to overlook.
- Web pages and Marp slides did not open in the expected preview.
- The role of an IDE and its tools was not always clear.

---

<div class="eyebrow">03 / Solutions Implemented</div>

## Make the Workflow Predictable

- Review Explorer exclusion settings and make hidden project files visible when needed.
- Remove an unintended `README.md` exclusion from the workspace settings.
- Use **Todo Highlight** to make `TODO` and `FIXME` comments easy to spot.
- Use **Live Server** for a local web preview that refreshes after edits.
- Enable the **Marp** extension and preview Markdown slides in VS Code.
- Treat VS Code as an IDE by combining editing, extensions, terminal, and previews.

---

<!-- _class: light -->

<div class="eyebrow">04 / Practical · Explorer</div>

## Show the Files You Need

1. Open **Settings** and search for `files.exclude`.
2. Review workspace exclusions for `.git` and `README.md`.
3. Remove an unwanted exclusion, or set that pattern to `false` in `settings.json`.

```json
{
  "files.exclude": {
    "**/.git": false,
    "**/README.md": false
  }
}
```

<p class="small">Only change exclusions that are hiding files you need. Keep repository metadata visible only when it helps your workflow.</p>

---

<div class="eyebrow">05 / Practical · Code reminders</div>

## Turn Comments Into Signals

Install **Todo Highlight**, then leave recognizable markers beside unfinished work:

```javascript
// TODO: validate the form before saving
function saveForm() {
  // FIXME: handle a failed response
}
```

The extension highlights matching keywords in the editor, making follow-up work easier to find.

---

<!-- _class: light -->

<div class="eyebrow">06 / Practical · Web preview</div>

## Run Live Server

1. Install the **Live Server** extension.
2. Open the project’s HTML entry point.
3. Select **Go Live** in the VS Code status bar.
4. Edit and save the page; the browser preview refreshes automatically.

<div class="callout">Use a local preview to check changes quickly—no manual refresh after each save.</div>

---

<div class="eyebrow">07 / Practical · Slides</div>

## Preview a Marp Deck

Keep Marp metadata at the top of the Markdown file:

```yaml
---
marp: true
theme: default
paginate: true
size: 16:9
---
```

Install the **Marp for VS Code** extension, open the deck, and use the Markdown preview. The `marp: true` setting tells Marp to render the document as slides.

---

<!-- _class: light -->

<div class="eyebrow">08 / The Bigger Picture</div>

## What Is an IDE?

**IDE** means **Integrated Development Environment**: a workspace that brings common development tools together.

### VS Code in this lab

- **Editor** — write and navigate source files.
- **Extensions** — add Todo Highlight, Live Server, and Marp.
- **Terminal** — run project commands.
- **Previews** — inspect web pages and slide decks while editing.

<p class="small">VS Code becomes more useful when its tools work together around the project—not just as a place to type code.</p>
