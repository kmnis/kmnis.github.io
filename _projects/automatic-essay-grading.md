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

Automatic Essay Grading is an NLP project for evaluating essays written by English Language Learners. The goal is not just to assign a single score, but to reason across multiple writing dimensions that teachers already use when assessing proficiency.

The project uses a dataset of argumentative essays from 8th-12th grade students. Each essay has scores for cohesion, syntax, vocabulary, phraseology, grammar, and conventions, making it a useful benchmark for multi-dimensional writing assessment.

### What The Project Does

- Processes and analyzes student essay text.
- Models six writing-proficiency dimensions rather than a single overall grade.
- Includes exploratory data analysis, preprocessing, data mining, and ML notebooks.
- Uses topic modeling experiments to understand essay patterns.
- Provides a notebook-based evaluator app for score-oriented feedback and analysis.

### Dataset

The dataset contains 3,911 essays written by English Language Learners. The essays were pre-scored by teachers across six analytic measures, with scores ranging from 1 to 5 in half-point increments.

This structure makes the task more nuanced than generic essay scoring. A strong answer may have good vocabulary but weaker grammar, or strong cohesion but limited phraseology. The project is organized around preserving that multi-axis view of writing proficiency.

### Modeling Workflow

The repository separates preprocessing, visualization, modeling, and the evaluator app. The modeling notebooks explore machine-learning and NLP approaches, while the data mining notebook includes topic modeling experiments with BERTopic.

The app layer demonstrates how essay text can be turned into feedback and analysis, rather than leaving the work as notebook-only modeling output.

### Example Workflows

The included screenshots show an evaluator interface, essay scoring output, and essay analysis. These examples help make the project concrete: the system is meant to support writing assessment workflows, not simply train a model in isolation.

### Limitations

Automated writing assessment should be used carefully. Scores can help triage or support feedback, but they should not replace teacher judgment, especially for English Language Learners. Bias, prompt variation, rubric alignment, and explainability all matter in a real educational setting.
