---
layout: project
title: Automatic Essay Grading
subtitle: NLP support for evaluating English learner essays
summary: "An NLP and machine-learning project for scoring English Language Learner essays across cohesion, syntax, vocabulary, phraseology, grammar, and conventions."
year: "2023"
status: "Open source prototype"
project_sort_order: 4
permalink: /projects/automatic-essay-grading
repo_url: https://github.com/kmnis/automatic-essay-grading
image: /_images/projects/automatic-essay-grading.png
image_alt: "Automatic essay evaluation result screen"
image_background: "linear-gradient(180deg, #DAE0C9 0%, #E3E8D1 52%, #E8E9D8 100%)"
tech_stack:
  - Python
  - NLP
  - Machine learning
  - BERTopic
  - OpenAI API
  - Jupyter
tags:
  - nlp
  - education
  - machine-learning
  - data-mining
highlights:
  - Writing assessment workflow for 3,911 pre-scored ELL essays across six analytic measures.
  - Preprocessing, exploratory analysis, data mining, topic modeling, and ML notebooks.
  - Notebook-based evaluator app that produces score-oriented feedback and essay analysis.
collaborators:
  - name: Manish Kumar
    url: https://www.linkedin.com/in/kmnis/
gallery:
  - url: https://raw.githubusercontent.com/kmnis/automatic-essay-grading/main/images/evaluator-app1.png
    alt: "Essay evaluator input screen"
  - url: https://raw.githubusercontent.com/kmnis/automatic-essay-grading/main/images/evaluator-app2.png
    alt: "Essay evaluation scoring screen"
  - url: https://raw.githubusercontent.com/kmnis/automatic-essay-grading/main/images/evaluator-app3.png
    alt: "Essay analysis screen"
related_projects:
  - docscribe
  - covid19-literature-analysis
  - zen-ai
---

Automatic Essay Grading focuses on a real education problem: writing practice is hard to scale, and English Language Learners need feedback that reflects their current language level rather than a generic writing rubric.

The project uses a dataset of 3,911 argumentative essays written by 8th-12th grade English Language Learners. Each essay is scored across six analytic measures: cohesion, syntax, vocabulary, phraseology, grammar, and conventions. The repository includes preprocessing, exploratory analysis, data mining, ML modeling, and a notebook-based evaluator app.

### Technical Shape

The repository is divided into `data_prep`, `data_viz`, `modeling`, and `app` directories. The evaluator app uses an OpenAI token for its final interaction layer, while the modeling notebooks explore classical NLP and machine-learning approaches.

### Why It Matters

The strongest use case is teacher support: speed up assessment cycles while preserving a richer view of student strengths and weaknesses across multiple dimensions of writing proficiency.
