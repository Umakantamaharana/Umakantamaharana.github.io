---
layout: post
title: "Can AI Respect Company Secrets? Introducing OrgAccess"
date: 2025-05-27 10:00:00
description: "We built OrgAccess to test if LLMs can follow real-world corporate access rules. Even top frontier models like GPT-4.1 struggled badly when multiple workplace permissions collided."
tags: ai-safety enterprise-ai benchmarks llm access-control
categories: research
featured: true
giscus_comments: true
related_posts: true
---

Every company today seems to want an "omnipresent AI assistant"—a smart bot connected to Slack, Google Drive, internal wikis, Jira, and customer databases, ready to answer any employee question in milliseconds.

It sounds magical until you consider how real organizations actually operate.

In any real workplace, information isn't a free-for-all. An engineering intern shouldn't be able to look up executive compensation. A marketing contractor in Berlin shouldn't access medical records of hospital clients in California. A sales manager might have access to quarterly pipeline data, but only for their region, and only during active business quarters.

If you give an LLM access to your company's knowledge base, **can you trust it to enforce those boundaries?**

To find out, our team at RespAI Lab, in collaboration with researchers from NUS, TCS Research, and BITS Pilani, created [**OrgAccess**](https://arxiv.org/abs/2505.19165) — a benchmark designed specifically to test role-based access control (RBAC) in organization-scale language models.

---

### In Plain English: The 60-Second Summary

> **The Problem:** Companies are connecting AI to all their private files so employees can search company knowledge quickly. But different employees have different clearance levels. If the AI doesn't know when to say "No," sensitive data leaks instantly.
>
> **What We Built:** **OrgAccess**, a testing suite of **70,000 workplace scenarios** based on real-world US government security standards (NIST). We tested 16 leading AI models to see if they could correctly decide whether to approve, deny, or partially approve employee requests.
>
> **What We Found:** For simple rules ("John is an intern; interns cannot view salary sheets"), models did well. But in the real world, rules stack up—departments, time limits, location tags, and project boundaries. When faced with 5 realistic overlapping rules, even frontier models like **GPT-4.1 crashed to an F1-score of only 0.27** (out of 1.0).
>
> **The Takeaway:** Today's smartest models cannot reliably juggle complex workplace permission rules. Putting an LLM in charge of enterprise data without strict external guardrails is a recipe for data leaks.

---

### Why Standard AI Benchmarks Missed This

Most existing AI benchmarks evaluate models on trivia, math competitions, Python coding, or general chat helpfulness. Those benchmarks measure raw intelligence or factual recall.

Real-world enterprise access control is fundamentally different. It requires **strict compositional reasoning under conflicting constraints**:
- A user might satisfy 4 out of 5 required conditions, but missing that 5th condition means a hard **REJECT**.
- A query might be phrased politely or sound urgent ("My manager needs this urgently for the 2 PM meeting!"), yet the model must coldly refuse if permissions don't allow it.
- Permissions often overlap or contradict each other, requiring the system to evaluate precedence accurately.

Because corporate security policies are proprietary and sensitive, researchers previously lacked a large, realistic public benchmark to test these capabilities.

---

### How We Built OrgAccess

We grounded OrgAccess in the **NIST (National Institute of Standards and Technology)** access control principles, covering **40 distinct permission types** commonly found across enterprise sectors:
- **Role and Department Boundaries:** Finance, Legal, HR, Engineering, R&D.
- **Action Scopes:** Read-only, write, audit, export, delete.
- **Contextual Restrictions:** Geographic location restrictions, network boundaries, session timeouts, and project deadlines.
- **Collaboration Overrides:** Shared joint-venture access with partial disclosure rules.

From this foundation, we generated **70,000 test cases** across three difficulty tiers:
1. **Easy (40,000 cases):** 1 clear permission rule tested in isolation.
2. **Medium (10,000 cases):** 3-permission tuples where multiple conditions must be synthesized.
3. **Hard (20,000 cases):** 5-permission tuples with overlapping, nested, and conflicting constraints.

---

### The Reality Check: What Happened When We Tested 16 Models?

We put 16 models—including proprietary frontier systems (like GPT-4o, GPT-4.1) and top open-weight models (like LLaMA and Mistral variants)—to the test.

Here is what the data revealed:

1. **The Single-Rule Illusion:** On the "Easy" single-permission split, most frontier models scored comfortably above 85-90%. They understand individual words like "confidential" or "marketing team."
2. **The Multi-Constraint Cliff:** As soon as multiple rules collided (e.g., role allows access, but location is outside the approved country and the session window expired 10 minutes ago), model performance dropped off a cliff.
3. **The Hardest Split:** On the 5-constraint test set, **GPT-4.1 achieved an F1-score of just 0.27**. Models either succumbed to "helpfulness bias" (granting access because the user asked nicely) or panicked and rejected legitimate employees who met every criteria.

---

### Where Do We Go From Here?

This benchmark makes one thing very clear: **you cannot simply write a system prompt saying "Be careful with permissions" and expect an LLM to safeguard enterprise secrets.**

Until models develop stronger formal reasoning over nested constraints, enterprise AI architectures need a hybrid approach:
- Hard deterministic authorization layers (like traditional RBAC policy engines) to verify permissions before the LLM ever touches the data.
- Dedicated guardrail models trained explicitly on negative constraint satisfaction.
- Comprehensive auditing against benchmarks like OrgAccess before deploying internal tools.

We are excited to share that this work has been accepted at **EMNLP 2025**, and both the full dataset and evaluation scripts are completely open-source.

---

### Explore the Benchmark

- 📄 **Paper on arXiv:** [https://arxiv.org/abs/2505.19165](https://arxiv.org/abs/2505.19165)
- 🤗 **Dataset on Hugging Face:** [https://huggingface.co/datasets/respai-lab/orgaccess](https://huggingface.co/datasets/respai-lab/orgaccess)
- 💻 **Code on GitHub:** [https://github.com/respailab/orgaccess](https://github.com/respailab/orgaccess)
