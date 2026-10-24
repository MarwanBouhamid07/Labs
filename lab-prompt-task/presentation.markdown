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
    content: "P";
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

# Prompt Task

---

<!-- _class: light -->

## Lab Plan

1. Introduction
2. Problems Encountered
3. Solutions Implemented

---

<div class="eyebrow">01 / Introduction</div>

## Give AI a Clear Task

A **prompt** is the instruction and context provided to an AI system. This lab explores how to shape a prompt so the response is relevant, useful, and easy to evaluate.

### In this lab

- Define the task and intended audience.
- Supply relevant context and constraints.
- Specify the response format.
- Refine a prompt using the response as feedback.

---

<!-- _class: light -->

<div class="eyebrow">02 / Problems Encountered</div>

## Why a Prompt Can Miss the Mark

No specific blocking incidents were included in the lab materials. Common prompt-writing challenges to watch for include:

- A vague request leaves the expected result open to interpretation.
- Missing context can produce generic or irrelevant answers.
- Conflicting instructions make priorities unclear.
- No length or format guidance can make the response hard to use.
- A fluent answer may still contain unsupported or incorrect claims.

---

<div class="eyebrow">03 / Solutions Implemented</div>

## Make the Request Testable

- State one clear task and the desired outcome.
- Include only the context needed to complete it.
- Set audience, tone, scope, and constraints where relevant.
- Describe the expected response format.
- Check the answer against the request and reliable sources.
- Revise the prompt when the response misses a requirement.

---

<!-- _class: light -->

<div class="eyebrow">04 / Practical · Prompt structure</div>

## Build a Reusable Prompt

```text
Task: [What should the AI do?]
Context: [What does it need to know?]
Audience: [Who is the answer for?]
Constraints: [What should it include or avoid?]
Format: [How should the answer be organized?]
```

<div class="callout">A prompt does not need every field. Add the details that materially affect the answer.</div>

---

<div class="eyebrow">05 / Practical · Be specific</div>

## From Vague to Actionable

### Vague

```text
Explain Git.
```

### More useful

```text
Explain the difference between `git commit` and `git push`
to a beginner. Use plain language, one short example for each,
and finish with a two-row comparison table.
```

The improved prompt names the audience, scope, examples, and output format.

---

<!-- _class: light -->

<div class="eyebrow">06 / Practical · Add context</div>

## Give the Model What It Needs

```text
Task: Draft a short announcement about a website maintenance window.
Context: The site will be unavailable on Tuesday from 18:00 to 18:30 UTC.
Audience: Existing customers.
Constraints: Be calm and direct; do not promise that the work will finish early.
Format: A subject line and a message under 100 words.
```

Relevant details reduce guesswork. Avoid adding private or sensitive information that is not needed.

---

<div class="eyebrow">07 / Practical · Set boundaries</div>

## Constraints Improve Fit

Constraints can define:

- **Scope:** What the response should cover.
- **Length:** A word limit or number of bullet points.
- **Tone:** Formal, friendly, neutral, or technical.
- **Audience:** Beginner, specialist, customer, or teammate.
- **Exclusions:** Topics or assumptions to leave out.

<div class="callout">Prefer precise, compatible constraints. If requirements conflict, clarify which one takes priority.</div>

---

<!-- _class: light -->

<div class="eyebrow">08 / Practical · Iterate</div>

## Treat the First Answer as a Draft

1. Write the prompt and review the response.
2. Identify what is missing, unclear, or out of scope.
3. Change the prompt to address that specific gap.
4. Compare the new response against the original requirements.

```text
Follow-up: Keep the same audience and topic, but shorten the answer
to three bullets and include one concrete example.
```

---

<div class="eyebrow">09 / Practical · Evaluate</div>

## Check Before You Use the Answer

| Check | Question |
|:---|:---|
| Relevance | Does it answer the task? |
| Completeness | Did it follow every required point? |
| Accuracy | Can factual claims be verified? |
| Format | Is the result in the requested structure? |
| Safety | Does it expose private data or make risky assumptions? |

An effective prompt helps guide an answer; it does not guarantee that the answer is correct.

---

<!-- _class: light -->

<div class="eyebrow">10 / Key Takeaway</div>

## Clear Input, Better Direction

**Task** &nbsp; + &nbsp; **context** &nbsp; + &nbsp; **constraints** &nbsp; + &nbsp; **format** &nbsp; → &nbsp; **more useful response**

<p class="small">Be specific, iterate on observable gaps, and verify important output before relying on it.</p>
