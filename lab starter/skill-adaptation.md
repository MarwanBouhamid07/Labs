# Lab Adaptation Skill — Standard Marp Presentation Structure

## Purpose
Adapt and realize any lab deliverable into a consistent, modern Marp presentation while strictly preserving the required structural flow and technical accuracy.

---

## Mandatory Slide Structure

Every lab presentation **must be in Marp format** (`marp: true`) and follow this sequential slide structure:

### Slide 1: Title (Lab Name Only)
- **Content:** The title / name of the lab **only**.
- **Rule:** **Never** include author or presenter names, student IDs, organization names, or extra sub-headers on Slide 1 unless explicitly requested.

### Slide 2: Lab Plan
- **Content:** The agenda of the presentation, strictly formatted as:
  ```markdown
  <!-- _class: light -->

  ## Lab Plan

  1. Introduction
  2. Problems Encountered
  3. Solutions Implemented
  ```

### Slide 3: Introduction
- Briefly explain the purpose, scope, and objectives of the lab based on the topic.
- List the key concepts, tools, or syntax practiced during the lab.

### Slide 4: Problems Encountered
- Include concrete technical issues, obstacles, syntax pitfalls, or configuration challenges relevant to the lab.
- If no incidents occurred, explicitly state that no blocking technical problems were encountered.

### Slide 5: Solutions Implemented
- Document concrete solutions, fixes, and best practices applied to resolve each problem or ensure compliance.

### Subsequent Slides: Practical Examples & Implementation
- Include practical code blocks, commands, syntax demonstrations, diagrams, or tables **directly inside the Marp presentation slides**.
- **Rule:** Do **not** create separate exercise or companion `.md` files; integrate all practical deliverables into the presentation.

---

## Marp Presentation & Design Standards

1. **Always Use Marp:**
   - Every lab must be formatted for Marp with valid YAML frontmatter:
     ```yaml
     ---
     marp: true
     theme: default
     paginate: true
     size: 16:9
     style: |
       ...
     ---
     ```
2. **Slide Separators:**
   - Use `---` between every slide.
3. **Alternating Visual Rhythm:**
   - Alternate between dark background sections (standard) and light background sections (`<!-- _class: light -->`) to maintain audience engagement and high readability.
4. **Typography & Code:**
   - Clear headings (`Anton`, `Impact`, or sans-serif).
   - High contrast body text (`Inter`, system-ui).
   - Always declare syntax languages for code blocks (e.g., ```` ```html ````, ```` ```javascript ````, ```` ```bash ````, ```` ```php ````).
   - Properly format Markdown tables with explicit column alignment (`:---`, `:---:`, `---:`).

---

## Operational Guidelines

- **No Presenter Names:** Keep the cover slide focused strictly on the lab topic.
- **Single Deliverable File:** Keep all documentation and examples inside the designated lab file (e.g. `lab-<topic>.md`).
- **No Unnecessary Git Inquiries:** Commit and push cleanly when requested without running redundant inspection loops.