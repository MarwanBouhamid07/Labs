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
    font-size: 24px;
    padding: 48px 66px;
    justify-content: center;
  }

  h1, h2 {
    color: #f7fbff;
    font-family: Anton, Impact, "Arial Narrow", sans-serif;
    font-weight: 400;
    line-height: 1;
    margin: 0 0 24px;
  }

  h1 { font-size: 94px; }
  h2 { font-size: 58px; }

  h3 {
    color: #56d6c2;
    font-size: 26px;
    margin: 0 0 10px;
  }

  ul, ol {
    font-size: 26px;
    line-height: 1.34;
  }

  li { margin-bottom: 10px; }
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
    font-size: 18px;
    line-height: 1.32;
    padding: 16px 20px;
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
    justify-content: center;
    overflow: hidden;
  }

  section.title::before {
    color: rgba(86, 214, 194, 0.09);
    content: "M";
    font-family: Anton, Impact, sans-serif;
    font-size: 440px;
    line-height: 0.8;
    position: absolute;
    right: 70px;
    bottom: -50px;
  }

  section.title h1 {
    font-size: 150px;
    position: relative;
    z-index: 1;
  }

  .eyebrow {
    color: #56d6c2;
    font-size: 17px;
    font-weight: 700;
    letter-spacing: 3px;
    margin-bottom: 18px;
    text-transform: uppercase;
  }

  .small {
    font-size: 19px;
    line-height: 1.35;
  }

  .callout {
    border-left: 5px solid #56d6c2;
    margin-top: 18px;
    padding: 8px 0 8px 16px;
  }
---

<!-- _class: title -->

# Markdown

---

<!-- _class: light -->

## Lab Plan

1. Introduction
2. Problems Encountered
3. Solutions Implemented

---

<div class="eyebrow">01 / Introduction</div>

## Write Once, Read Anywhere

**Markdown** is a lightweight markup language for formatting plain-text documents. Its simple symbols make source files easy to write while producing readable, structured content.

### In this lab

- Create headings, paragraphs, and emphasis.
- Organize information with lists, links, images, and tables.
- Write inline code, fenced code blocks, and task lists.
- Preview Markdown and check its rendered output.

---

<!-- _class: light -->

<div class="eyebrow">02 / Problems Encountered</div>

## Small Syntax, Common Mistakes

- Missing spaces after heading markers can prevent a heading from rendering.
- Inconsistent indentation can break nested lists and task lists.
- Unmatched emphasis markers or backticks can format more text than intended.
- Incorrect link or image paths create broken references.
- Code fences without a language label lose syntax highlighting.
- Markdown flavors differ; a feature may render differently across platforms.

---

<div class="eyebrow">03 / Solutions Implemented</div>

## A Reliable Writing Workflow

- Use a space after `#` and keep heading levels in order.
- Indent nested list items consistently.
- Pair each `**`, `*`, or backtick marker and preview the result.
- Check URLs and image paths, including capitalization and file extensions.
- Label code fences with a language such as `javascript` or `html`.
- Preview in the target editor or platform before sharing.

---

<!-- _class: light -->

<div class="eyebrow">04 / Practical · Headings & text</div>

## Structure and Emphasis

Use headings to show document hierarchy. Separate paragraphs with a blank line, and add emphasis only where it helps readers scan.

```markdown
# Project Guide

## Getting Started

Install the dependencies before running the app.

**Important:** Keep your configuration file private.
Use *italics* for a light emphasis.
```

<div class="callout">Use one top-level heading for the document title, then increase heading depth without skipping levels.</div>

---

<div class="eyebrow">05 / Practical · Lists</div>

## Make Steps Easy to Follow

### Unordered list

```markdown
- Plan the page
- Write the content
  - Add examples
  - Review the preview
```

### Ordered steps

```markdown
1. Install the editor extension.
2. Open the Markdown preview.
3. Check the rendered page.
```

---

<!-- _class: light -->

<div class="eyebrow">06 / Practical · Links & images</div>

## Connect Related Resources

```markdown
[Open the project repository](https://github.com/)

![A descriptive image caption](images/diagram.png)
```

- Link text should describe the destination.
- Use a correct relative or absolute image path.
- Add descriptive alt text so the image has a text alternative.
- Confirm external links and local assets work in the published location.

---

<div class="eyebrow">07 / Practical · Code</div>

## Show Code Clearly

Use single backticks for inline code and triple backticks for a fenced block. Add a language identifier after the opening fence.

````markdown
Run `npm install` to install dependencies.

```javascript
const message = "Hello, Markdown!";
console.log(message);
```
````

---

<!-- _class: light -->

<div class="eyebrow">08 / Practical · Tables & tasks</div>

## Summarize and Track

```markdown
| Format | Common use |
|:-------|:-----------|
| Markdown | Documentation |
| HTML | Web pages |

- [x] Draft the content
- [x] Add examples
- [ ] Review the preview
```

Tables and task-list checkboxes are supported by many, but not all, Markdown renderers.

---

<div class="eyebrow">09 / Preview & Share</div>

## Check the Rendered Document

1. Save the file with a `.md` or `.markdown` extension.
2. Open the Markdown preview in your editor.
3. Inspect headings, lists, links, images, and code formatting.
4. Check the document in its destination platform.
5. Fix broken references and crowded or confusing sections.

<div class="callout">The rendered page is what readers see. Preview it before you publish or share it.</div>

---

<!-- _class: light -->

<div class="eyebrow">10 / Key Takeaway</div>

## Plain Text, Clearly Structured

Markdown combines a small set of readable conventions:

**Text** &nbsp; + &nbsp; **simple syntax** &nbsp; + &nbsp; **a renderer** &nbsp; → &nbsp; **formatted content**

<p class="small">Start with clear structure, use consistent syntax, and preview the result on the platform where it will be read.</p>
