# Physiotherapy Lecture Knowledge Base

A structured, searchable knowledge base built from my university physiotherapy lecture
materials (London Met, BSc Physiotherapy). The repository pairs each original lecture
file with a Markdown version so it can be used by Claude for revision, flashcards, MCQs,
OSCE prep, clinical cases and summaries — while the original files remain the
authoritative source.

## Layout

The repository keeps its established year/module structure. Each original lecture now has
a Markdown companion **in the same folder**:

```
Lectures/
  First Year/
    MSK/
      Hand anatomy PT7001-4054 - 24-25.pptx      <- original (authoritative)
      Hand anatomy PT7001-4054 - 24-25.md        <- Markdown knowledge file
      ...
  Second Year/
    Cardio Resp/ | MSK/ | Neuro/ | Other/{Other, Professionalism, Practice Education}/
INDEX.md          <- navigable map of everything, linking to the .md files
README.md         <- this file
_REVIEW/          <- items needing human confirmation (see below)
```

Original PDF/PPTX/DOCX/XLSX files are **never deleted or overwritten**. The `.md` file is a
convenience layer; if the two ever disagree, the original wins.

## Year / module classification

Classification follows the module codes in the material, which map cleanly to UK academic
levels:

| Code      | Level    | Year   |
|-----------|----------|--------|
| `PT4xxx`  | Level 4  | Year 1 |
| `PT7xxx` / `ST7xxx` | Level 7 (pre-registration, co-taught) | Year 1 |
| `PT5xxx`  | Level 5  | Year 2 |

Every file whose filename carries a code sits in the matching year. Where a file has no
code, placement follows the existing (WebLearn-derived) folder structure.

## Markdown format & metadata

Every `.md` file begins with YAML front matter:

```yaml
---
title: "Hand anatomy"
academic_year: "Year 1"
module: "MSK"
topic: "unknown"
source_file: "Lectures/First Year/MSK/Hand anatomy PT7001-4054 - 24-25.pptx"
source_type: "PPTX"
module_codes: ["PT4054", "PT7001"]
lecture_number: "unknown"
classification_confidence: "High"
---
```

- **classification_confidence** — `High` (a module code corroborates the year),
  `Medium` (placement from folder/WebLearn, no code), or `Low` (flagged in `_REVIEW`).
- **duplicate_of** — lists other copies / other-format versions when they exist.
- **review** — present only when the file is flagged for human confirmation.
- Unknown fields are marked `unknown` rather than guessed. Lecture numbers are never
  invented; a `week:` field appears only when the filename states a week number.

The body preserves the lecture's structure — slide/page headings, bullet lists, tables and
speaker notes — extracted from the original. Content is not rewritten or summarised.

## Images

Image extraction and OCR/transcription of educationally important diagrams (anatomy,
pathophysiology, imaging, graphs, algorithms, framework diagrams) is a **planned follow-up
phase**. A small number of slide decks are image-based with little extractable text; these
are noted at the top of their `.md` file and listed in `_REVIEW/Conversion-Issues`.

## `_REVIEW/`

Items that need a human decision — nothing here has been moved or deleted:

- **Uncertain-Year/** — files kept in place but whose slide text hints at a different year
  (mainly foundational anatomy/physiology in `Second Year/MSK`). Awaiting confirmation.
- **Possible-Duplicates/** — identical files, same-text copies, and PDF/PPTX pairs.
  Sequential parts (Part 1/Part 2) are deliberately not treated as duplicates.
- **Conversion-Issues/** — image-only decks and one legacy `.doc` that need the image phase
  or manual handling.

## Using this repository with Claude

The Markdown files are the primary searchable knowledge representation. Start from
`INDEX.md` to locate a topic, open the relevant `.md`, and cite the `source_file` from its
metadata. The original files preserve full fidelity (exact figures, formatting); the images
phase will add the visual content that text alone cannot carry.
