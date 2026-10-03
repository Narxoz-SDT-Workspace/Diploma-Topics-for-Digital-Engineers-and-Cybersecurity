# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Not a code project: there is no build, lint or test tooling. It is a planning workspace for choosing the 8 BSc diploma topics (programme: Digital Engineering + Cybersecurity, NARXOZ 2026-27) that fill Үкібасов Баубек's empty slots, rows 114–121 of the department sheet. Work is tracked in Linear (workspace `Narxoz`, team `SDT-Baubek`, project `P-SDT-2`, issues SDT-1 … SDT-8) and the artefacts are markdown notes in `notes/`.

## Source data

`Бакалавриат_Темы_дипломных_проектов.xlsx - Бакалавриат.csv` is a Google Sheets export, kept **local and gitignored** (`.gitignore`). Do not commit it.
- Columns: `ФИО` (supervisor), `Тақырып (қазақша)`, `Тема (русский)`, `Title (English)`, `Оқу бағдарламасы (ОП)`.
- One row = one topic slot. `ФИО` and `ОП` are filled only on the first row of each supervisor block (merged cells in the source), so forward-fill them before grouping.
- Row numbers used everywhere in `notes/` are sheet rows (header = row 1), not CSV indices.
- 157 slots: 101 real topics, 2 placeholders ("stealth mode startup idea", rows 58–59), 54 empty. Other supervisors' empty slots may fill in; re-run the SDT-2 scan before SDT-6.

## Linear issue chain

SDT-1 rubric → SDT-2 landscape scan → SDT-3 discussion #1 → SDT-4 long-list → SDT-5 scoring → SDT-6 discussion #2 (shortlist, final 8) → SDT-7 per-topic briefs (sub-issues) → SDT-8 trilingual titles and sheet fill. Blocking relations in Linear follow this order. As of 2026-10-03, SDT-1 to SDT-5 are Done; SDT-6 to SDT-8 are open. Check Linear for the current state.

## Where the decisions live

Read these before proposing or scoring anything; they supersede earlier assumptions.
- `notes/SDT-1-rubric-draft.md`: the scoring rubric (v3). Weights: commercial 0.30, MVP reachability 0.25, agent-buildability 0.10, modularity 0.10, differentiation 0.10, programme fit 0.10, supervisor fit 0.05. Gates: MVP, programme fit, modularity ≤ 2 drops a topic.
- `notes/SDT-3-decision-record.md`: no quotas per direction; seed areas are Security of ML / MLOps, Data engineering / analytics, LLM agents and tooling; allowed business models B2B, B2C, open-source + service, B2B2C; partner and private-data topics are allowed (the earlier "open data only" rule was withdrawn); each topic records a data / partner mode and partner status.
- `notes/SDT-2-landscape.md`: 14 clusters of the existing 101 topics, with the saturated areas (phishing/scam, IDS, RAG assistants, personal-finance apps, LLM monitoring) and the gaps.
- `notes/SDT-4-longlist.md` and `notes/SDT-5-scoring.md`: the 25 candidates and their scores. Scores are judgement, not market research.

## Project constraints that shape every topic

- Product-first: the deliverable is a working MVP with a UI (mobile, web or desktop); a CLI or API alone does not count. Scientific novelty is not scored, but each thesis still needs a measurable evaluation.
- Topics are built by a **group** of students, group size variable: N = number of independent modules, one module per student as the basis of individual assessment. Development time up to 6 months.
- Students must use an agentic coding tool (Claude Code or Codex), so topics must be agent-buildable with a shared spec and automated tests as contracts between modules.
- Target market: KZ / Central Asia first, global niches allowed. "Pilot user" means someone outside the student's circle; a paying customer is not required.

## Open items

- **Naming:** Narxoz SDT has rules for naming diploma projects, and they have not been provided yet. All titles in the notes are working names. Do not write final KZ/RU/EN titles (SDT-8) until the user supplies the rules.
  - Checked `Diploma-work-requirements/` (2026-10-03): the diploma-project regulations (RU, KZ) and the APA guides contain **no** naming rules: no structure, length limit, required words, language requirements or forbidden words. Only mentions: "наименование темы проекта" is a field of the project passport (п. 4.5; the 700-character limit in п. 9.4 covers the whole passport, not the title), defence may be in any teaching language (п. 8.6), and APA says a title should be clear and concise, without abbreviations or empty words, one or two lines (RUS guide, title-page section only; KZ/ENG guides not checked).
  - **Working assumptions (user's department experience, not confirmed by any document):** (1) the title must fully reflect what is developed and delivered, with no length limit; (2) it contains "Разработка" / "Әзірлеу" / "Development of…". Sheet check (2026-10-03, 101 filled topics): "разработ-" / "әзірле-" / "develop-" appears in 55 of 101 / 101 / 103 titles (other verbs: создание 2, проектирование 2, внедрение 1; жасау 1, құру 1, енгізу 1), so it is common but not universal. "Система" and "платформа" occur freely in existing titles, and no prohibition is visible there. RU titles average ~99 characters, max 151. Case, trilingual requirement and ban on brands/trademarks remain unknown.
  - The only unread source is `Онлайн-встреча с научными руководителями.mp4` (~10 min); the user chose to skip the audio. Remaining routes: ask the school / programme head.
- Several scoring points are waiting for SDT-6: no Security-of-ML candidate in the top 10, the C5/A6 overlap, C1's required security angle, partner dependence of E1/E3, and the legal check for D4.

## Working conventions

- Language of replies is Russian; notes and Linear text have been written in English, code and identifiers always in English.
- Nothing has been committed. Commit only when the user asks. `notes/` contains supervisors' names and sheet row numbers, so decide whether to ignore it if the repo ever becomes public.
