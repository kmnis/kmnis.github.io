---
layout: project
title: COVID-19 Literature Analysis
subtitle: ML and graph workflows for navigating CORD-19 research
summary: "A machine-learning pipeline for clustering and exploring COVID-19 research papers using CORD-19, PySpark, Hadoop, topic modeling, and graph database experiments."
year: "2022"
status: "Open source analysis"
project_sort_order: 2
permalink: /projects/covid19-literature-analysis
repo_url: https://github.com/kmnis/covid19-literature-analysis
image: /_images/projects/covid19-lit-analysis-project-image.png
image_alt: "COVID-19 literature analysis methodology"
image_background: "linear-gradient(180deg, #EDF6FE 0%, #EAF4FD 55%, #E7F2FC 100%);"
license: MIT
tech_stack:
  - Python
  - PySpark
  - Hadoop
  - Neo4j
  - GraphFrames
  - Topic modeling
tags:
  - covid-19
  - machine-learning
  - nlp
  - graph-database
highlights:
  - CORD-19 preprocessing pipeline for nested JSON papers and metadata.
  - Topic modeling workflow for clustering similar papers and surfacing major research themes.
  - Graph database experiments for author-paper-journal relationships with Neo4j and PySpark GraphFrames.
collaborators:
  - name: Manish Kumar
    url: https://www.linkedin.com/in/kmnis/
gallery:
  - url: https://raw.githubusercontent.com/kmnis/covid19-literature-analysis/main/images/data_prep.png
    alt: "CORD-19 data preprocessing pipeline"
  - url: https://raw.githubusercontent.com/kmnis/covid19-literature-analysis/main/images/final-graph.png
    alt: "COVID-19 literature graph visualization"
  - url: https://raw.githubusercontent.com/kmnis/covid19-literature-analysis/main/images/topic1.png
    alt: "Topic modeling result example"
related_projects:
  - docscribe
  - zen-ai
  - automatic-essay-grading
---

The CORD-19 dataset gave researchers a massive, fast-growing corpus of coronavirus literature. This project asks a practical question: how can researchers move through that body of work without reading every paper linearly?

The pipeline parses nested JSON papers and metadata, prepares the data for distributed processing, and applies topic modeling to group similar publications. The project also explores graph representations, where authors, papers, and journals become nodes connected by publishing relationships.

### Technical Shape

The repository is organized around data preparation, visualization, graph database exploration, and modeling notebooks. A Docker-backed Neo4j workflow imports author-paper-journal relationships, while topic modeling examples summarize distinct research clusters.

### Why It Matters

Scientific literature becomes more valuable when its structure is searchable. This project turns a large research corpus into a set of navigable themes and relationships.
