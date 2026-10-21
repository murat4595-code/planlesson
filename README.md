# Maarif Lesson Planner (version 2.0)

Curriculum-constrained lesson plan generator for English language teachers implementing the Century of Türkiye Education Model (Türkiye Yüzyılı Maarif Modeli), Grades 9–12.

**Live:** https://murat4595-code.github.io/maariflessonplanner/

Online Resource 1 for: *Algorithmic Scaffolding for Curricular Fidelity: A Conceptual Analysis of a Generative AI Lesson Planning Tool Aligned with the Century of Türkiye Education Model* (SN Social Sciences).

## How it works

The whole tool is one static page, `index.html`, served by GitHub Pages. There is no server.

- **Curricular data:** `TOPICS_BY_GRADE`, `GRAMMAR_BY_GRADE`, `MAARIF_OUTCOMES` and `DROPDOWN_OPTIONS` restrict the selectable themes, grammar points, coded outcomes and options to the official curriculum.
- **AI service** (`window.MaarifAI`, plain JavaScript inside `index.html`): builds the prompts (`SYSTEM_PROMPT`, `buildUserPrompt`) and streams the lesson plan from the OpenRouter API.
- **API key:** each user enters their own free OpenRouter key (https://openrouter.ai/keys). It is stored only in that user's browser (localStorage) and sent only to openrouter.ai. No key is stored in this repository.

## Models

Free models only, tried in order until one accepts the request (temperature 0.7, up to 8,000 output tokens):

1. `google/gemma-4-31b-it:free` (reasoning disabled)
2. `minimax/minimax-m3.1-flash:free` (reasoning required by the model; kept at low effort and hidden)
3. `openrouter/free` (OpenRouter's router restricted to free models)

Version 1.x called the preview model `gemini-2.5-flash-preview-09-2025` with an API key written into the page; version 2.0 removed the key from the code and uses free models only.

No personal or student data are requested or stored.
