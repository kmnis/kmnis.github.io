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

DocScribe is a prototype medical assistant for working with clinical reports. The idea is simple: instead of making someone manually scan long reports, discharge notes, or visit histories, the system lets them ask questions and get report-aware answers.

The project explores two related use cases. First, it helps explain and summarize a single medical report. Second, it makes patient history easier to search across multiple visits, so relevant findings, treatments, adverse reactions, and follow-up details can be retrieved conversationally.

### What DocScribe Does

- Answers general medical questions using a medical-domain language model workflow.
- Accepts medical transcripts and reports as context for patient-specific questions.
- Summarizes information across reports, including treatment plans and visit history.
- Retrieves relevant details from patient history instead of relying only on a model's general memory.
- Demonstrates workflows for report analysis, medical coding, adverse reactions, PDF inputs, and general QA.

### System Design

DocScribe combines retrieval with language-model reasoning. Uploaded reports are transformed into text, embedded, and indexed so that relevant chunks can be retrieved when a user asks a question. The retrieved context is then passed into the question-answering layer, keeping the answer grounded in the supplied medical material.

The prototype interface is notebook-based, which makes the workflow easy to inspect: upload or select reports, create embeddings, ask questions, and review the generated answers. LangChain and Hugging Face are used around the retrieval and model workflow.

### Data And Model

The project uses a mix of medical transcript and reference-style datasets:

- MTSamples medical transcripts
- WikiDoc medical reference data
- WikiPatient patient-facing medical information
- Around 4.5k generated question-answer pairs from medical transcripts

The model workflow is built around Vicuna-13B with LoRA, PEFT, and bitsandbytes. This keeps the fine-tuning setup more practical while still adapting the model toward medical question answering and report interpretation.

### Example Workflows

The repository includes examples for questions like: What does this transcript say about the patient's treatment plan? What adverse reactions are mentioned? Are there possible report errors? What medical codes may be relevant? How can multiple visits be summarized?

Those examples are useful because they show the project as more than a chatbot. The core pattern is report-grounded QA: the system should use the supplied medical context, not just produce a plausible medical-sounding response.

### Limitations

DocScribe is a prototype, not a clinical decision-support system. Medical QA has high safety and privacy requirements, so a system like this would need expert validation, stronger evaluation, careful handling of protected health information, and guardrails around uncertainty before any real clinical use.
