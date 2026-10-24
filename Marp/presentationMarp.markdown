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

# Marp

---

<!-- _class: light -->

## Lab Plan

1. Introduction
2. Problems Encountered
3. Solutions Implemented

---

<div class="eyebrow">01 / Introduction</div>

## Slides, Written in Markdown

**Marp** turns Markdown into presentation slides. Instead of designing each slide in a visual editor, write headings, lists, code, and slide directives in a text file, then preview or export the deck.

### In this lab

- Configure a Markdown file as a Marp presentation.
- Separate and style slides with Marp directives.
- Preview and export the finished deck.

---

<!-- _class: light -->

<div class="eyebrow">02 / Problems Encountered</div>

## Common Setup Pitfalls

- Without `marp: true` in the YAML front matter, a file may be treated as ordinary Markdown.
- A misplaced or unclosed `---` can break front matter or split slides unexpectedly.
- Markdown preview and Marp slide preview are easy to confuse.
- Long content or large code blocks can overflow a slide.
- Code fences without a language label lose useful syntax highlighting.

---

<div class="eyebrow">03 / Solutions Implemented</div>

## A Reliable Marp Workflow

- Put valid YAML front matter at the very start of the file.
- Use `---` on its own line between slides, outside code fences.
- Open the Marp preview with the Marp extension in VS Code.
- Keep each slide focused; split dense material across slides.
- Add a language identifier to every code fence.
- Export to HTML or PDF after checking the deck in preview.

---

<!-- _class: light -->

<div class="eyebrow">04 / Practical · Configuration</div>

## Start With Front Matter

Place this configuration at the top of the presentation file:

```yaml
---
marp: true
theme: default
paginate: true
size: 16:9
---
```

`marp: true` enables Marp for the document. `theme`, `paginate`, and `size` set a baseline appearance, slide numbers, and widescreen format.

---

<div class="eyebrow">05 / Practical · Slide structure</div>

## Separate Slides With `---`

Write each slide in Markdown and put the separator between slides:

```markdown
# What is Marp?

Write slides with familiar Markdown.

---

## A second slide

- Add a heading
- Add a list
```

Keep separators out of fenced code blocks when they are meant to divide slides.

---

<!-- _class: light -->

<div class="eyebrow">06 / Practical · Directives</div>

## Set a Slide’s Appearance

Marp supports directives in HTML comments. A local class can change one slide:

```markdown
<!-- _class: lead -->

# A focused title slide
```

Global directives belong in front matter; local directives apply to individual slides. The selected theme and CSS determine how a class such as `lead` looks.

---

<div class="eyebrow">07 / Practical · Code</div>

## Keep Examples Readable

Use fenced code blocks with a language identifier:

```javascript
const presentation = {
  format: "Markdown",
  slides: 8
};

console.log("Ready to present");
```

Choose a short example and leave enough space around it. If a slide feels crowded, move details to the next slide.

---

<!-- _class: light -->

<div class="eyebrow">08 / Preview & Export</div>

## From Markdown to Slides

1. Install **Marp for VS Code**.
2. Open the `.md` or `.markdown` presentation.
3. Open the Marp preview and inspect every slide.
4. Fix overflow, contrast, and code formatting.
5. Export to **HTML** or **PDF** when ready to share.

<div class="callout">Preview first, export second: the rendered slides—not just the source—are the final deliverable.</div>

---

<div class="eyebrow">09 / Key Takeaway</div>

## Markdown In. Slides Out.

Marp keeps presentation content portable and easy to edit:

**Markdown** &nbsp; + &nbsp; **slide separators** &nbsp; + &nbsp; **Marp directives** &nbsp; → &nbsp; **presentation**

<p class="small">Start with clear content, use a consistent design, and let the preview catch layout issues before presenting.</p>
