---
name: update-cv
description: >-
  Triggered when the user updates their CV PDF file at files/Tulio_CV.pdf.
  This skill guides the agent to read the new PDF file, extract its text, and
  update the markdown CV page at _pages/cv.md accordingly.
---

# Update CV Page from PDF

## Overview
This skill automates updating the markdown CV page (`_pages/cv.md`) whenever the user replaces their CV PDF file at `files/Tulio_CV.pdf`. It ensures the online CV text matches the PDF document while retaining formatting, responsiveness, and links.

## Workflow

### 1. Read the new PDF CV
- Use the `view_file` tool on `d:/Github/tuliofalmeida.github.io/files/Tulio_CV.pdf`.
- Review the OCR/extracted text page by page. Note down new publications, work history, skills, or contact info.

### 2. Prepare the cv.md update
- Open `d:/Github/tuliofalmeida.github.io/_pages/cv.md` to see the existing front matter.
- Retain the Jekyll front matter (permalink, layout, title, and the PDF download button):
  ```yaml
  ---
  layout: single
  title: "Curriculum Vitae"
  header:
    overlay_image: mineirao.png
    overlay_filter: 0.3
  permalink: /cv/
  author_profile: true
  share: true
  redirect_from:
    - /resume
  ---

  <a href="{{ site.baseurl }}/files/Tulio_CV.pdf" class="btn btn--info" target="_blank"><i class="fa fa-file-pdf-o" aria-hidden="true"></i> Download CV (PDF)</a>
  ```
- Translate the parsed PDF content into clean, responsive Markdown:
  - Use `##` for main sections (Education, Experience, Technical Skills, Publications, etc.).
  - Use bullet points (`*`) for details, using bolding for titles.
  - Link any DOIs or URLs directly.
  - Fix any common OCR typos.

### 3. Write and Save
- Overwrite `_pages/cv.md` with the new markdown using `write_to_file` (set `Overwrite` to `true`).

### 4. Push to GitHub
- Verify the changes locally.
- Run terminal command: `git add _pages/cv.md; git commit -m "Update CV page from PDF"; git push origin master`
- Notify the user that their website is updating and will be live in a minute.

## Common Mistakes
- **Losing the Jekyll Header:** Do not overwrite the front matter at the top of `_pages/cv.md`.
- **Using PDF embed:** Do not use `embed` tags for the CV text. Keep the CV as raw Markdown text, and only link the PDF via the download button.
- **Incorrect PDF Path:** Ensure the PDF download button links to `{{ site.baseurl }}/files/Tulio_CV.pdf`.
