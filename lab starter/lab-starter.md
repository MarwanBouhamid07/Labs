---
marp: true
theme: default
paginate: true
size: 16:9
style: |
  @import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');

  section {
    background: #70020f;
    color: #ffe0e3;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 26px;
    padding: 50px 60px;
    text-transform: uppercase;
    justify-content: flex-start;
  }

  h1, h2 {
    font-family: 'Anton', Impact, 'Arial Narrow', sans-serif;
    font-weight: 400;
    color: #ffe0e3;
    line-height: 0.98;
    letter-spacing: -1px;
    margin: 0 0 28px 0;
  }

  h1 { font-size: 100px; }
  h2 { font-size: 68px; }

  h3 {
    font-size: 28px;
    margin: 0 0 10px 0;
    color: #e6d9dc;
  }

  p { margin: 0 0 12px 0; }

  section.light {
    background: #ffdde0;
    color: #70020f;
  }

  section.light h1,
  section.light h2,
  section.light h3 {
    color: #70020f;
  }

  section.light p,
  section.light li {
    color: #111;
  }

  section.title {
    justify-content: space-between;
  }

  section.title h1 {
    font-size: 116px;
    margin-top: 8px;
  }

  section.title::before {
    content: "DEV\\A ENV";
    white-space: pre;
    position: absolute;
    right: -15px;
    bottom: 10px;
    font-family: 'Anton', Impact, sans-serif;
    font-size: 250px;
    line-height: 0.85;
    color: #5f0010;
    z-index: 0;
  }

  section.title h1,
  section.title .by {
    position: relative;
    z-index: 1;
  }

  .by {
    font-size: 20px;
    text-transform: none;
    margin-top: 20px;
  }

  .by strong {
    font-family: 'Anton', Impact, sans-serif;
    font-weight: 400;
    text-transform: uppercase;
    font-size: 27px;
    display: block;
  }

  ul, ol {
    font-size: 30px;
    line-height: 1.35;
  }

  li { margin-bottom: 12px; }

  code {
    background: rgba(255, 224, 227, 0.13);
    padding: 2px 7px;
    border-radius: 4px;
    text-transform: none;
  }

  section.light code {
    background: rgba(112, 2, 15, 0.09);
  }

  .subtitle {
    font-size: 25px;
    color: #e6d9dc;
    text-transform: none;
  }

  .small {
    font-size: 21px;
    line-height: 1.35;
    text-transform: none;
  }

  .step {
    font-family: 'Anton', Impact, sans-serif;
    font-size: 31px;
    color: #ffe0e3;
  }

  section.light .step {
    color: #70020f;
  }
---

<!-- _class: title -->

# Development<br>Environment

<div class="by">
  <strong>Mohammed Yassir Mesbahi</strong>

encadre:essarraj-fouad 
</div>

---

<!-- _class: light -->

## Lab Plan

1. Problems encountered during the lab
2. Showing hidden files and folders
3. Making `README.md` visible
4. Using Todo Highlight for code reminders
5. Installing and using Live Server
6. Configuring Marp Markdown Preview
7. Meaning of IDE and why we use it

---

## Problems Encountered

- Hidden files and folders, such as `.git`, were not visible in the file explorer.
- The `README.md` file was not displayed as expected.
- We sometimes forgot which lines of code needed to be modified.
- Marp presentation files did not open in the expected preview.

---

<!-- _class: light -->

## Solutions Implemented

### 01 — Show hidden files

Enabled the relevant file-explorer setting so hidden files and folders, including `.git`, could be seen.

### 02 — Display README.md

Adjusted the relevant VS Code option/extension setting so `README.md` appeared in the explorer.

### 03 — Remember code changes

Installed **Todo Highlight** to highlight important comments and reminders in the code.

---
<!-- TODO: -->
<!-- _class: light -->

## Solutions Implemented

### 04 — Preview web pages

Installed **Live Server** to launch a local development server and automatically refresh web pages after changes.

### 05 — Preview Marp slides

Installed/configured the **Marp extension** so Markdown presentation files could be viewed in slide preview.
## 05- Meaning of IDE and why we use it