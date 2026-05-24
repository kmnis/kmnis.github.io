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
  - url: https://raw.githubusercontent.com/kmnis/covid19-literature-analysis/main/images/methodology.png
    alt: "COVID-19 literature analysis methodology"
  - url: https://raw.githubusercontent.com/kmnis/covid19-literature-analysis/main/images/final-graph.png
    alt: "COVID-19 literature graph visualization"
related_projects:
  - docscribe
  - zen-ai
  - automatic-essay-grading
---

COVID-19 Literature Analysis is a machine-learning project for exploring the CORD-19 research corpus. The goal is to make a large collection of coronavirus-related papers easier to search, cluster, and understand.

The project combines data preprocessing, topic modeling, distributed data workflows, and graph database experiments. Instead of treating the literature as a flat list of papers, it explores both thematic clusters and relationships between papers, authors, and journals.

### What The Project Does

- Parses CORD-19 JSON papers and metadata into analysis-ready data.
- Uses topic modeling to group similar publications and surface major themes.
- Explores PySpark and Hadoop-oriented workflows for larger-scale literature processing.
- Models paper-author-journal relationships as a graph.
- Demonstrates graph storage and visualization with Neo4j and PySpark GraphFrames.

### Data Pipeline

CORD-19 includes nested JSON files for papers plus metadata files with additional publication information. The preprocessing workflow converts that raw structure into cleaner tabular data that can be used for modeling and visualization.

The repository includes both Python and PySpark preprocessing work. This makes the project useful as a literature-analysis experiment and as a small example of how scientific text data can be prepared for distributed processing.

### Modeling And Graph Analysis

Topic modeling is used to identify clusters of related papers. The sample outputs in the repository show themes such as immune response and antibodies, pandemic effects on society and mental health, and infection detection or virus-related research.

The graph workflow represents papers, authors, and journals as nodes connected by relationships such as publication and authorship. This makes it possible to explore the research landscape structurally, not just textually.

### Results

The project includes visual outputs for preprocessing, methodology, graph views, and topic examples. Together, they show a workflow for turning a large research corpus into navigable themes and relationships.

### Limitations

Topic modeling is exploratory. It can reveal useful themes, but the resulting clusters still need human interpretation. The project is best read as an analysis and navigation prototype rather than a definitive map of COVID-19 research.
