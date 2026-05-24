---
layout: project
title: ZenAI
subtitle: AI mental health counselor prototype
summary: "A conversational support prototype that combines fine-tuned LLM behavior, intent detection, model evaluation, and a Streamlit user experience for mental-health-adjacent conversations."
year: "2023"
status: "Research prototype"
role: "Modeling, evaluation, and product experience"
project_sort_order: 0
permalink: /projects/zen-ai
repo_url: https://github.com/zenn-ai/zen
image: /_images/projects/zen-ai-project-image.png
image_alt: "ZenAI welcome screen artwork"
image_background: "linear-gradient(180deg, #FDF3EA 0%, #F8EDE4 55%, #F9F1EA 100%)"
github_stars: 7
github_forks: 2
tech_stack:
  - Python
  - Vicuna-13B
  - Llama 2
  - PaLM/Bison
  - Streamlit
  - Intent detection
tags:
  - generative-ai
  - llm
  - mental-health
  - streamlit
highlights:
  - Fine-tuned and evaluated a therapy-oriented conversational model against baseline LLM behavior.
  - Built an intent-detection layer to route sensitive or unsupported prompts more deliberately.
  - Designed a user-facing Streamlit experience and documented risks, testing, and future safety work.
collaborators:
  - name: Manish Kumar
    url: https://www.linkedin.com/in/kmnis/
  - name: Deepak Vanjani
    url: https://www.linkedin.com/in/deepakvanjani/
  - name: Danil Meresenschi
    url: https://www.linkedin.com/in/dmeresenschi/
  - name: Puneet Modi
    url: https://www.linkedin.com/in/puneet3modi/
gallery:
  - url: https://github.com/zenn-ai/therapy-bot/assets/97678601/f0b3bec3-3de8-4e73-a5ea-af7922a8705b
    alt: "ZenAI overview diagram"
  - url: https://github.com/zenn-ai/therapy-bot/assets/97678601/e624ce36-8004-4ef8-92a2-eaa84b78aed2
    alt: "ZenAI testing summary"
  - url: https://github.com/zenn-ai/therapy-bot/assets/97678601/19a119e2-afe5-404d-a6dc-40d786a7befb
    alt: "ZenAI user experience preview"
related_projects:
  - docscribe
  - automatic-essay-grading
  - comicface-ai
---

ZenAI explores what it takes to move a general conversational model toward a more careful, supportive dialogue experience. The project was not just a chatbot wrapper; it included data preparation, model training, inference notebooks, intent detection, quantitative evaluation, qualitative response testing, and a Streamlit interface.

The most interesting part of the work is the product boundary. Mental-health-adjacent AI needs more than fluent answers, so the project explicitly treated risks and future safeguards as part of the system. The README documents model metrics, intent-detection evaluation over labeled prompts, user testing snippets, and the team’s safety-oriented future work.

### What I Worked On

- Helped build and evaluate the LLM workflow for supportive conversations.
- Worked through model inference and testing paths, including intent classification.
- Contributed to the UX direction so the model could be experienced as a product rather than a notebook-only experiment.

### Technical Shape

The repository separates the project into data, training, inference, utilities, and UX. The modeling stack centers on large language models such as Vicuna-13B and Llama 2, with supporting notebooks for evaluation and intent handling. The frontend prototype lives in Streamlit.

### Why It Matters

This project is a good example of turning a sensitive AI idea into a system design problem: dataset quality, model behavior, evaluation, product experience, and risk management all had to be considered together.
