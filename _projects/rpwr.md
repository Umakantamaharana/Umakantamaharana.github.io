---
layout: page
title: "Right Prediction, Wrong Reasoning"
description: "Uncovering LLM Misalignment in Rheumatoid Arthritis Disease Diagnosis: AI models can achieve high classification accuracy while generating clinically flawed medical explanations."
img: "assets/img/publication_preview/rpwr.png"
date: 2025-04-10
importance: 3
category: research
badge: "Healthcare AI Safety"
arxiv: "2504.06581"
---

# Right Prediction, Wrong Reasoning: Uncovering LLM Misalignment in RA Disease Diagnosis

<div class="mb-3">
  <span class="badge badge-warning p-2" style="font-size: 0.9rem; background-color: #f29105; color: #fff;">Healthcare AI Safety</span>
  <span class="badge badge-secondary p-2 ml-2" style="font-size: 0.9rem;">Clinical Evaluation</span>
  <span class="badge badge-info p-2 ml-2" style="font-size: 0.9rem;">arXiv:2504.06581</span>
</div>

Large Language Models (LLMs) are increasingly being explored for medical diagnostic assistance. However, high benchmark accuracy can be deceptively reassuring. In this clinical study, we demonstrate that LLMs frequently predict the correct Rheumatoid Arthritis (RA) diagnosis while relying on clinically dangerous, hallucinated, or specious justifications.

---

### Direct Links & Resources

- 📄 **arXiv Paper:** [https://arxiv.org/abs/2504.06581](https://arxiv.org/abs/2504.06581)
- 📑 **PDF:** [https://arxiv.org/pdf/2504.06581.pdf](https://arxiv.org/pdf/2504.06581.pdf)

---

### Authors & Collaborators

- [Umakanta Maharana](https://umakantamaharana.github.io/)
- [Sarthak Verma](https://scholar.google.com/)
- [Avarna Agarwal](https://scholar.google.com/)
- [Prakashini Mruthyunjaya](https://scholar.google.com/)
- [Dwarikanath Mahapatra](https://scholar.google.com/)
- [Sakir Ahmed](https://scholar.google.com/)
- [Murari Mandal](https://openreview.net/profile?id=~Murari_Mandal1)

---

### Key Findings

- **Accuracy vs. Explanation Disconnect:** LLMs achieved >90% diagnostic classification accuracy on RA clinical notes, but blinded physician review revealed that over 68% of the generated reasoning steps contained critical factual errors or non-standard diagnostic criteria.
- **The "Right for the Wrong Reasons" Risk:** A model providing the right diagnosis for flawed reasons undermines clinical trust and poses severe safety risks if deployed without human-in-the-loop expert validation.
- **Clinical Alignment Need:** Highlights the urgent need for evaluation benchmarks that assess diagnostic justification faithfulness rather than just top-1 accuracy.
