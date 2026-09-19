---
layout: page
title: "OrgAccess"
description: "A Benchmark for Role-Based Access Control in Organization-Scale LLMs — testing whether models can reliably respect organizational roles, permissions, and access boundaries."
img: "assets/img/publication_preview/orgaccess.png"
date: 2025-05-25
importance: 1
category: research
related_publications: true
github: https://github.com/respailab/orgaccess
---

# OrgAccess: A Benchmark for Role-Based Access Control in Organization-Scale LLMs

<span class="badge badge-primary p-2" style="font-size: 0.9rem; background-color: #1a5fb4;">Accepted at EMNLP 2025</span>

We introduce **OrgAccess**, a benchmark for evaluating role-based access control in organization-scale LLMs, focusing on whether models can reliably respect organizational roles, permissions, and access boundaries. OrgAccess puts 16 frontier and open models against real enterprise-style access rules — **40 NIST-grounded permission types**, **70K instances**, and **up to 5 conflicting constraints** at once.

---

### Direct Links & Resources

- 📄 **arXiv Paper:** [https://arxiv.org/abs/2505.19165](https://arxiv.org/abs/2505.19165)
- 🤗 **Hugging Face Dataset:** [https://huggingface.co/datasets/respai-lab/orgaccess](https://huggingface.co/datasets/respai-lab/orgaccess)
- 💻 **GitHub Repository:** [https://github.com/respailab/orgaccess](https://github.com/respailab/orgaccess)

---

### Authors & Collaborators

- [Debdeep Sanyal](https://debdeepsanyal.com)
- [Umakanta Maharana](https://umakantamaharana.github.io/)
- [Hong Ming Tan](https://thm.sg)
- [Yash Sinha](https://openreview.net/profile?id=~Yash_Sinha1)
- [Shirish Karande](https://openreview.net/profile?id=~Shirish_Karande1)
- [Mohan Kankanhalli](https://www.comp.nus.edu.sg/cs/people/mohan/)
- [Dhruv Kumar](https://kudhru.github.io/)

---

### Overview & Highlights

- **Role-Based Access Control (RBAC):** Investigates whether LLMs can reliably operate within complex, hierarchical organizational structures and enforce strict access boundaries.
- **Enterprise-Scale Complexity:** Defines 40 distinct types of permissions grounded in NIST access control standards across diverse roles and departments.
- **Dataset Structure (70,000 instances):**
  - **Easy (40,000 cases):** Single-permission queries to assess baseline permission understanding.
  - **Medium (10,000 cases):** 3-permission tuples testing composite reasoning.
  - **Hard (20,000 cases):** 5-permission tuples with overlapping, nested, and conflicting constraints.
- **Key Finding:** Frontier models exhibit severe limitations in hierarchical enterprise access compliance — even **GPT-4.1 achieves an F1-Score of only 0.27** on the hardest benchmark split.
