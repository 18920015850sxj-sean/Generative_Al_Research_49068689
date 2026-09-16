# Generative_Al_Research_49068689

Repository of REIT6811 Applied Class — a mixed-methods study on generative AI in higher
education, combining a literature review, a quantitative survey strand, a qualitative
interview strand, and the resulting drafts and reports.

> **Status: scaffold.** Everything except this README, `.gitignore` and the `.gitkeep` files is a
> zero-byte placeholder. Each placeholder marks *where* a deliverable belongs and what to call it.
> Replace the placeholders with the real documents as the project progresses.

## Repository structure

| Folder | What lives here |
| --- | --- |
| `01_Literature_Review/` | Sources and notes, split by publication type: `journal_articles/`, `conference_papers/`, `books/`, `newspaper_articles/`. |
| `02_Quantitative_Analysis/` | The survey strand end to end: `survey_instrument/` (items and scales), `data_raw/` (read-only exports), `data_processed/` (cleaned data), `scripts/` (Python analysis code), `outputs/` (figures and tables), `reports/` (survey write-up). |
| `03_Qualitative_Analysis/` | The interview strand: `protocols/` (interview guides), `consent_forms/` (templates only), `transcripts/` (de-identified, pseudonymised), `coding/` (codebooks and coding files), `reports/` (insight reports), `visualisations/`. |
| `04_Drafts_and_Reports/` | Outward-facing writing: `proposals/`, `conference_papers/`, `final_reports/`. |
| `05_Additional_Materials/` | Supporting assets: `information_sheets/`, `photos/`, `media/`. |
| `06_Admin/` | Project administration, currently `meeting_notes/`. |

## Navigating the repository

The numbered prefixes are the reading order: literature → analysis → writing → supporting
material → admin. Work inside the folder that matches the stage you are at, rather than creating
new top-level folders — if nothing fits, raise it in a meeting first.

Within `02_Quantitative_Analysis/`, the data flow is one-directional:

```
survey_instrument/ → data_raw/ → data_processed/ → outputs/ → reports/
                        ↑              ↑
                    read-only      written by scripts/
```

`data_raw/` is **append-only and never edited**: cleaning decisions belong in `scripts/`, so any
number can be regenerated from source. Never overwrite a file in `data_processed/` or `outputs/`;
write a new version instead.

## File naming convention

```
YYYYMMDD_topic_detail_vNN.ext
```

Examples: `20260915_survey_cleaned_v02.csv`, `20260701_interview_protocol_v01.docx`.

Use the date the file was *created*, keep the topic in lower snake case, and bump `vNN` for every
revision. Dates sort chronologically, versions do not overwrite each other, and nobody has to
guess which `final_final` is actually final.

## Data governance — read before committing

- **Never commit signed consent forms, identifiable transcripts, recordings, or raw data
  containing personal information.** Signed forms are stored in UQRDM; only the blank template
  belongs in `03_Qualitative_Analysis/consent_forms/`.
- Transcripts in this repository must be pseudonymised (participants referred to as P01, P02, …)
  and stripped of identifying details before they are added.
- De-identified analysis files may be committed so the analysis is reproducible.
- If a file should not be public, add it to `.gitignore` and confirm with the team before
  committing anything that touches participant data.

## Contributing

1. **Branch.** Do not commit directly to `main`. Create a short-lived branch:
   `git switch -c analysis/survey-descriptives` or `docs/lit-review-notes`.
2. **Commit in small, labelled steps.** Prefix the subject with the area you touched — `lit:`,
   `quant:`, `qual:`, `drafts:`, `materials:`, `admin:` — and write it in the imperative:
   `quant: add cleaned survey data and initial analysis scripts`. One logical change per commit.
3. **Keep data and code changes separate.** A commit that changes `scripts/` should not also
   drop in new `data_raw/` files.
4. **Open a pull request** against `main` and request a review from at least one team member
   before merging. Describe what changed and why in the PR body.
5. **Report issues in the meeting notes**, not in commit messages — `06_Admin/meeting_notes/`
   is where decisions are recorded.

Questions about scope or folder placement go to the team before you create new structure.

## Getting started

```bash
git clone https://github.com/Geraniol/Generative_Al_Research_49068689.git
cd Generative_Al_Research_49068689
python -m venv .venv && source .venv/bin/activate   # for the analysis scripts
```
