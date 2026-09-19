---
layout: post
title: "Right Prediction, Wrong Reasoning: Why High Accuracy in Medical AI Can Be Dangerous"
date: 2025-04-11 11:00:00
description: "When we tested AI on diagnosing Rheumatoid Arthritis, it guessed the disease correctly 95% of the time. But real doctors found that 68% of its medical explanations were completely wrong."
tags: ai-safety healthcare llm medical-ai
categories: research
giscus_comments: true
related_posts: true
---

If a medical student guesses the right illness on a multiple-choice exam, but when asked _why_, explains that the patient's blood pressure matches their shoe size, you would not let them near a hospital ward.

Yet in modern artificial intelligence, we do something uncomfortably close to that almost every day. We feed clinical notes into a large language model, see a 90%+ diagnostic accuracy number on a test set, celebrate the benchmark score, and assume the model "understands" medicine.

Our recent study, [_"Right Prediction, Wrong Reasoning: Uncovering LLM Misalignment in RA Disease Diagnosis"_](https://arxiv.org/abs/2504.06581), looked beneath that shiny hood. What we found should give anyone pause before deploying AI models as clinical pre-screening assistants.

---

### In Plain English: The 60-Second Summary

> **The Problem:** Many clinics lack specialist doctors, especially in rural areas, making it hard to catch autoimmune diseases like Rheumatoid Arthritis early. People hope AI chatbots can help screen patients.
>
> **What We Tested:** We gave real patient records to AI models to see if they could diagnose Rheumatoid Arthritis, and we asked the models to write down their clinical reasoning step-by-step.
>
> **The Catch:** The AI correctly named the condition roughly **95% of the time**. But when experienced rheumatologists read the written explanations, **nearly 68% of those explanations were clinically flawed, irrelevant, or fabricated**.
>
> **Why It Matters:** In medicine, getting the right answer by following bogus logic is a ticking time bomb. A doctor relying on flawed AI logic could miss critical complications or mistreat the next patient whose symptoms slightly differ.

---

### Why Rheumatoid Arthritis?

Early diagnosis of Rheumatoid Arthritis (RA) is both vital and notoriously difficult. In its early stages, symptoms look like ordinary fatigue, aches, or standard joint stiffness. By the time visible joint erosion appears on an X-ray, irreversible damage has often already happened.

Specialists rely on a delicate web of signals: symmetric joint swelling, morning stiffness lasting hours, specific antibody markers (like RF and anti-CCP), inflammatory markers (ESR, CRP), and careful patient history. In many parts of the world, rheumatologists are scarce, making LLM-driven pre-screening an enticing proposal.

We wanted to answer a simple, grounded question: **If an LLM says a patient has RA, does it actually understand the medical evidence, or is it just making lucky pattern-matching guesses?**

---

### The Experiment: Putting Explanations to the Test

Working with clinical collaborators, we compiled real patient cases alongside expert diagnoses. We then evaluated several leading LLM agents across multi-round diagnostic interactions.

We didn't just ask the models for a "Yes" or "No." We forced them to generate step-by-step clinical rationales:

- Which specific clinical symptoms pointed to RA?
- How did the lab values factor into the conclusion?
- Why were alternative explanations (like osteoarthritis or viral arthritis) ruled out?

Then came the crucial step: **human medical specialists graded the model's explanations blindly.**

---

### The Findings: The Illusion of Competence

The quantitative results were striking:

1. **Top-line accuracy was stellar:** The best-performing model achieved roughly **95% accuracy** in identifying whether a patient had RA.
2. **The underlying reasoning collapsed:** Medical experts judged that **68% of the explanations were clinically unsound**.

The models repeatedly committed subtle, dangerous errors:

- **Spurious Correlations:** Attributing joint pain to laboratory values that had zero diagnostic relevance to autoimmune conditions.
- **Hallucinated Clinical Links:** Claiming that a standard, normal biomarker was "a hallmark sign of active synovial inflammation."
- **Inverted Logic:** Using the absence of a symptom as proof of the disease, or treating a negative test result as a confirmation.

Because the final word—"Diagnosis: Rheumatoid Arthritis"—happened to match the patient's actual chart, any automated metric that only looks at accuracy would have marked these runs as a 100% success.

---

### What Does This Mean for the Future of Medical AI?

This gap between **prediction** and **reasoning** is what we call _explanation misalignment_.

If an AI gives doctors the right answer along with plausible-sounding but false reasons, two bad things happen:

1. **Automation Bias:** A busy physician might glance at the accurate diagnosis, trust the confident tone, and miss that the model is hallucinating the clinical justification.
2. **Brittle Generalization:** A model relying on nonsense logic will inevitably fail when presented with complex real-world edge cases—such as a patient with overlapping lupus and arthritis, or atypical lab panels.

Before we rush to integrate language models into triage, pre-screening, or electronic health record workflows, accuracy metrics alone cannot be the finish line. We need rigorous evaluation protocols where domain specialists audit the entire chain of reasoning.

---

### Read the Full Paper

If you'd like to dive into the methodology, experimental design, and detailed clinical evaluation breakdown, you can read our full preprint:

- 📄 **arXiv:** [https://arxiv.org/abs/2504.06581](https://arxiv.org/abs/2504.06581)
- 📝 **Citation:** `arXiv:2504.06581 [cs.AI]`
