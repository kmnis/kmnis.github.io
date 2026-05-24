---
layout: project
title: ZenAI
subtitle: AI mental health counselor prototype
summary: "A conversational support prototype that combines fine-tuned LLM behavior, intent detection, model evaluation, and a Streamlit user experience for mental-health-adjacent conversations."
year: "2023"
status: "Research prototype"
project_sort_order: 0
permalink: /projects/zen-ai
repo_url: https://github.com/zenn-ai/zen
image: /_images/projects/zen-ai-project-image.png
image_alt: "ZenAI welcome screen artwork"
image_background: "linear-gradient(180deg, #FDF3EA 0%, #F8EDE4 55%, #F9F1EA 100%)"
tech_stack:
  - Python
  - Vicuna-13B
  - Llama 2
  - PaLM/Bison
  - Streamlit
  - Intent detection
highlights:
  - Therapy-oriented conversational prototype built around fine-tuned LLM behavior and response evaluation.
  - Intent-detection layer for routing sensitive or unsupported prompts more deliberately.
  - Streamlit user experience with documented risks, testing notes, and future safety work.
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

ZenAI is a research prototype for conversational mental-health support. It explores how a general large language model can be adapted into a more focused assistant with supportive response behavior, intent detection, evaluation, and a simple user experience.

The project is not framed as a replacement for professional care. Its value is in studying the pieces that would be needed for a safer support-oriented assistant: data preparation, model training, response evaluation, prompt/intent handling, and a product interface that makes the system easier to test.

### What ZenAI Does

- Provides a chatbot experience for supportive mental-health-adjacent conversations.
- Uses a fine-tuned LLM workflow rather than relying only on an off-the-shelf model.
- Adds intent detection to identify sensitive, unsupported, or differently routed prompts.
- Includes quantitative and qualitative evaluation of model responses.
- Packages the interaction into a Streamlit interface for user testing and demos.

### System Design

The repository separates the work into data, training, inference, utility, and UX layers. Training and inference notebooks handle the model workflow, while the UX folder contains the Streamlit app used to interact with the assistant.

The intent-detection layer is an important design choice. In a sensitive domain, the system needs more than a fluent response generator; it needs a way to recognize when a conversation requires caution, redirection, or a different response strategy.

### Data And Model

The project uses mental-health conversation data and generated dialogue data to adapt the assistant's behavior. The modeling work centers on large language models such as Vicuna-13B and Llama 2, with additional evaluation against baseline LLM responses.

The README also documents an intent-detection evaluation over labeled prompts, which helps show whether the system can recognize categories of user intent rather than treating every message as a normal open-ended chat turn.

### User Experience

ZenAI includes a Streamlit prototype that turns the model into a testable product experience. The UI matters because model behavior is easier to evaluate when users can interact with it as a real assistant instead of only reading notebook outputs.

### Limitations

Mental-health AI has high safety requirements. ZenAI should be understood as a research prototype, not a clinical tool. A production version would need expert review, safety guardrails, crisis-handling policies, privacy controls, stronger evaluation, and clear boundaries around what the assistant can and cannot do.
