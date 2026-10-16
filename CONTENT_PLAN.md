# Content overhaul plan

Goal: get the site ready for the PI job market. Search committees spend a minute or two here and
want to know: what's the research program, is it independent of my mentors, do I deliver
(papers, software, talks, funding), and will I be a good mentor and colleague.

Biggest gap: **the postdoc work isn't on the site.** The research themes cover my Master's
(Drosophila), PhD (landscapes) and methods, but not the marmoset census and genome, the *Cell*
paper, or inbreeding in South Asian populations.

Legend: 🤖 Claude can do it without input · ✍️ Claude drafts, I edit · 🙋 needs me

## 1. About Me

- [ ] ✍️ One-line tagline under my name saying what I study
- [ ] ✍️ Rewrite the bio around my own questions and where my lab is going (mentors in one sentence)
- [ ] 🤖 Role: "Computational Biologist" → "Postdoctoral Researcher" + department and institution
- [ ] 🤖 Add ORCID (0000-0001-7508-1384) to the profile icons

## 2. Research themes

Restructure into three themes that tell one story:

| Theme | Covers |
| --- | --- |
| **Primate population genomics** (current, lead) | marmoset census and genome, great-ape landscapes, South Asian inbreeding |
| **What shapes genomic variation** | landscapes across species, Drosophila clines and seasonal change, gene flow vs. selection (Miranda et al.) |
| **Simulation and inference tools** | stdpopsim, pyslim/SLiM, tskit 1.0, pg_gpu, deep learning on ancestral recombination graphs |

Each theme page: the question, my approach, one key result, **what's next**, a figure, its papers.

- [ ] ✍️ Draft the three theme pages
- [ ] 🙋 "What's next" for each theme
- [ ] 🙋 Figures, especially one for the marmoset work

## 3. Selected publications

- [ ] 🙋 Pick 4–5 papers to feature. Suggestion: census 2026, shared landscapes 2024,
      stdpopsim 2025 (MBE, co-first), pyslim 2025 (co-first), marmoset genome 2026 (*Cell*)
- [ ] 🙋 A key figure from each as a thumbnail
- [ ] 🤖 Featured list with thumbnails and role badges, then a link to the full filterable list
- [ ] 🤖 Replace the "filter publications" box with a plain link

## 4. New sections (from the CV)

- [ ] 🤖 **Software:** stdpopsim (core developer); tskit, msprime, pyslim, scikit-allel (contributor); pg_gpu
- [ ] 🤖 **Talks** page: SMBE 2023 and 2024 talks, ASP 2025 talk, posters, slide links
- [ ] 🤖 **Teaching & mentoring** block: Lewis & Clark guest lecture, TA courses, mentees
      (Vitória Miranda, Carlos Henrique Passos), service (reviewing for GENETICS, MBE, …)
- [ ] 🤖 **News:** ~8 dated items from 2025–2026 papers and talks; I keep adding new ones
- [ ] 🤖 **Fellowships & awards** (FAPESP fellowships, UO Genetics Training Grant, scholarships)
      on the About or CV page, not the homepage

## 5. Basics

- [ ] 🤖 Site title "MFR" → "Murillo F. Rodrigues" (browser tabs, Google results)
- [ ] 🤖 Rewrite the search-engine description in `config/_default/params.yaml`
- [ ] 🤖 Social-share image and favicon
- [ ] 🙋 Update the CV (dated Dec 2025, missing the four 2026 papers), then swap in
      `static/uploads/resume.pdf`

## Proposed homepage order

About Me → Research (3 themes) → Selected publications → Software → News → Teaching & mentoring

Separate pages, linked from the menu: Talks, all publications, CV.

## Sequence

1. **No input needed:** basics, ORCID, Software, Talks, News, Teaching & mentoring (one PR)
2. **Drafts to edit:** tagline options, research themes, bio rewrite
3. **Needs me:** "what's next" per theme, figures, selected papers, updated CV
