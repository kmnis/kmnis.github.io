---
layout: project
title: DocScribe
subtitle: Medical QA assistant for reports and patient history
summary: "A medical question-answering assistant that makes clinical reports easier to search, summarize, and understand using embeddings, LangChain/Hugging Face tooling, and a fine-tuned Vicuna model."
year: "2023"
status: "Open source prototype"
project_sort_order: 1
permalink: /projects/docscribe
repo_url: https://github.com/kmnis/DocScribe
image: /_images/projects/docscribe-project-image.png
image_alt: "DocScribe system architecture"
image_background: "linear-gradient(180deg, #FEFAF4 0%, #FEF9F2 55%, #FEF8F0 100%)"
license: MIT
tech_stack:
  - Python
  - LangChain
  - Hugging Face
  - Vicuna-13B
  - LoRA
  - PEFT
  - bitsandbytes
tags:
  - generative-ai
  - medical-ai
  - retrieval
  - llm
highlights:
  - Medical QA workflow for general questions, uploaded reports, and patient-specific history retrieval.
  - Training corpus combines medical transcripts, generated QA pairs, WikiDoc, and patient-facing medical data.
  - Vicuna-13B fine-tuning workflow using LoRA, PEFT, and bitsandbytes for medical-domain responses.
collaborators:
  - name: Manish Kumar
    url: https://www.linkedin.com/in/kmnis/
  - name: Kargil Thakur
    url: https://www.linkedin.com/in/kargil
  - name: Ekansh Trivedi
    url: https://www.linkedin.com/in/ekansh-trivedi
gallery:
  - url: https://raw.githubusercontent.com/kmnis/DocScribe/main/assets/images/sample-transcript-analysis-output.png
    alt: "DocScribe transcript analysis output"
  - url: https://raw.githubusercontent.com/kmnis/DocScribe/main/assets/images/treatment-plan.png
    alt: "DocScribe treatment plan response"
  - url: https://raw.githubusercontent.com/kmnis/DocScribe/main/assets/images/report-summary.png
    alt: "DocScribe report summary"
related_projects:
  - zen-ai
  - automatic-essay-grading
  - covid19-literature-analysis
---

DocScribe is a medical question-and-answer assistant designed around two practical needs: helping users understand individual medical reports, and making longitudinal patient history easier to retrieve and summarize.

The system combines a notebook-based web UI, embedding/index creation from medical transcripts, and LLM-based question answering. The training data combines medical transcripts, WikiDoc-style medical reference data, and patient-facing WikiPatient information. The README describes 4.5k generated QA prompts from medical transcripts and a Vicuna-13B fine-tuning workflow using LoRA, PEFT, and bitsandbytes.

### Technical Shape

The architecture uses embeddings and indexes to connect uploaded reports with a question-answering layer. LangChain and Hugging Face support the retrieval and model orchestration, while the interface uses Jupyter notebooks for upload and interaction workflows.

### Why It Matters

Medical information is dense, fragmented, and often hard for patients to interpret. DocScribe prototypes a more conversational layer over that information while keeping the report itself central to the answer.
