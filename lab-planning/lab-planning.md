---
name: lab-planning-technical-lab
description: Create or adapt technical lab presentations with a consistent six-slide structure for developers and DevOps, grounded in the supplied project evidence. Use when preparing a technical lab, presentation, or lab plan.
---

# Lab Planning — Prepare a Technical Lab (Development + DevOps)

## Purpose
Create or adapt a technical lab presentation for a real project. Help developers and DevOps engineers understand the project context, stack, key concepts, documented problems, implemented solutions, and verification tests.

Use the supplied lab notes, source files, task descriptions, logs, configuration, and user-provided facts as the source of truth. Never invent project-specific details.

## Required Presentation Structure
Use this six-slide structure by default, in this order, unless the user explicitly requests a change.

### Slide 1 — Project Title
- Display the actual project name.
- Add a short subtitle describing the technical lab, based on the source.
- Include presenter/team names only if supplied.
- Do not use a generic title when the real project name is available.

### Slide 2 — Lab Plan
Show a concise agenda:
1. Introduction / project context
2. Technical stack
3. Important definitions and concepts
4. Problems encountered
5. Solutions implemented
6. Tests and validation

This is an overview only. Do not put detailed explanations on this slide.

### Slide 3 — Technical Stack
- Name technologies actually used in the lab.
- For the initially specified lab, include Alpine.js and Laravel only if they are relevant to the supplied project.
- Explain each technology's role in this project in one short, accurate sentence.
- Include DevOps components (runtime, server, environment variables, containers, CI/CD, monitoring, infrastructure, etc.) only when supported by the supplied material.
- Do not imply that a tool was used just because it is common.
- If a component is unknown, mark it “not specified” or ask for clarification.

### Slide 4 — Important Definitions
Explain relevant technical terms or project concepts that may not be familiar to every developer.
- Use a simple definition plus why the concept matters in this project.
- Select terms from the supplied lab material, code, architecture, errors, or configuration.
- Explain Alpine.js or Laravel concepts only where relevant to the implementation.
- DevOps terms may include environment variables, build/runtime, reverse proxy, container, CI/CD, deployment, logs, or health checks, but include them only if they appear in or are needed to understand the lab.
- Avoid basic definitions the audience is expected to know.
- Do not turn this into a generic glossary. If too many terms are needed, prioritize the most important ones and ask before adding slides.

### Slide 5 — Problems Encountered
- Present up to five real problems, errors, blockers, or technical risks documented in the supplied material.
- Aim for five only when five are supported by evidence.
- For each problem, state the symptom/error and its context or impact if known.
- Prefer evidence from logs, screenshots, code, tests, or the user's notes.
- Do not invent problems just to reach five. If fewer than five are documented, show only those supported and say more evidence is needed.
- Distinguish actual problems from hypothetical risks.

### Slide 6 — Solutions and Tests
- Pair each documented problem with its corresponding solution.
- Include only fixes/actions actually applied or explicitly supplied by the user.
- Include tests/verification (commands, test cases, browser checks, HTTP status, logs, health checks, deployment verification) only when documented.
- If a fix or test is missing, label it “To confirm” or “Test not documented,” or ask the user. Never claim success without evidence.
- State status where possible: fixed and verified, fixed but not verified, unresolved, or not specified.
- Cover both development and DevOps where relevant, but do not force DevOps content when the lab has none.

## Audience and Technical Balance
Make the presentation useful to both:
- **Developers:** application behavior, code, framework/library responsibilities, implementation, errors, and tests.
- **DevOps engineers:** environment configuration, runtime/build, deployment, infrastructure, logs, health checks, automation, and operational validation.

Connect the two perspectives when the source supports it, such as verifying an application-level fix in its target environment. Do not add infrastructure claims without evidence.

