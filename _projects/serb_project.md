---
layout: page
title: "Machine Unlearning"
description: "Government of India (SERB) sponsored initiative (₹30.5 Lakh) investigating algorithmic data removal and privacy compliance in deep learning models without performance degradation. Successfully completed on January 1, 2026."
img: "assets/img/serb-project-bg.jpg"
date: 2024-05-25
category: funded
importance: 1
badge: "SERB Funded (Completed)"
---

<div class="serb-grant-hero">
  <div class="serb-hero-top">
    <div class="serb-emblem-icon">
      <i class="fa-solid fa-landmark-dome"></i>
    </div>
    <div class="serb-hero-titles">
      <h2>Science and Engineering Research Board (SERB)</h2>
      <p>Statutory Body Established Through an Act of Parliament: SERB Act 2008 &bull; Department of Science &amp; Technology (DST), Government of India</p>
    </div>
  </div>
  <div class="serb-grant-meta-tags">
    <span class="grant-pill status-completed"><i class="fa-solid fa-circle-check"></i> Project Completed</span>
    <span class="grant-pill"><i class="fa-solid fa-file-contract"></i> File No: SRG/2023/001686</span>
    <span class="grant-pill budget-highlight"><i class="fa-solid fa-indian-rupee-sign"></i> ₹30,50,300 (100% Released)</span>
    <span class="grant-pill"><i class="fa-solid fa-calendar-check"></i> 02-Jan-2024 &ndash; 01-Jan-2026</span>
    <span class="grant-pill"><i class="fa-solid fa-shield-halved"></i> Trustworthy AI</span>
  </div>
</div>

<div class="serb-metrics-grid">
  <div class="serb-metric-box">
    <div class="metric-label"><i class="fa-solid fa-indian-rupee-sign"></i> Total Budget</div>
    <div class="metric-val">₹30,50,300 INR</div>
    <div class="metric-sub">₹30,50,300 Released (100% Utilized)</div>
    <div class="metric-progress" title="100% Released">
      <div class="metric-progress-bar" style="width: 100%;"></div>
    </div>
  </div>

  <div class="serb-metric-box">
    <div class="metric-label"><i class="fa-solid fa-clock"></i> Duration &amp; Status</div>
    <div class="metric-val">24 Months</div>
    <div class="metric-sub">02-Jan-2024 &ndash; 01-Jan-2026 (Completed)</div>
  </div>

  <div class="serb-metric-box">
    <div class="metric-label"><i class="fa-solid fa-user-tie"></i> Principal Investigator</div>
    <div class="metric-val">Dr. Murari Mandal</div>
    <div class="metric-sub">Associate Professor, KIIT</div>
  </div>

  <div class="serb-metric-box">
    <div class="metric-label"><i class="fa-solid fa-building-columns"></i> Host Institution</div>
    <div class="metric-val">KIIT University</div>
    <div class="metric-sub">Bhubaneswar, Odisha, India</div>
  </div>
</div>

<div class="serb-section-card">
  <h3><i class="fa-solid fa-scale-balanced"></i> Regulatory Motivation &amp; Problem Statement</h3>
  <p>
    In contemporary deep learning systems, neural networks memorize intricate patterns directly from training distributions. However, emergent regulatory frameworks—including the European Union's General Data Protection Regulation (<strong>GDPR Article 17: "Right to be Forgotten"</strong>), the California Consumer Privacy Act (CCPA), and India's <strong>Digital Personal Data Protection (DPDP) Act 2023</strong>—legally mandate that individuals can revoke consent and demand complete removal of their personal data footprints from trained predictive models.
  </p>
  <p>
    The standard naive solution—retraining massive models from scratch while excluding the targeted data shards—is computationally prohibitive, financially unsustainable, and environmentally costly when scaling across billions of parameters. This research project, funded under the prestigious <strong>SERB Startup Research Grant (SRG)</strong>, investigated principled algorithmic frameworks to achieve <em>exact and approximate machine unlearning</em>. The objective was to surgically excise specific data influence from deep neural representations rapidly, while strictly preserving task utility and preventing catastrophic forgetting on retained distributions.
  </p>
</div>

<div class="serb-section-card">
  <h3><i class="fa-solid fa-compass-drafting"></i> Core Research Objectives</h3>
  <p>
    The project established both theoretical bounds and scalable empirical algorithms for efficient data erasure across dense deep learning architectures:
  </p>

  <div class="serb-objectives-grid">
    <div class="objective-box">
      <div class="obj-icon"><i class="fa-solid fa-eraser"></i></div>
      <h4>Targeted Parameter Scrubbing</h4>
      <p>Designing efficient first- and second-order weight adjustment algorithms that nullify the influence of requested samples without full model retraining.</p>
    </div>

    <div class="objective-box">
      <div class="obj-icon"><i class="fa-solid fa-shield-virus"></i></div>
      <h4>Catastrophic Forgetting Prevention</h4>
      <p>Formulating regularized feature constraints to guarantee that the decision boundaries of retained classes maintain high fidelity and zero-shot generalization.</p>
    </div>

    <div class="objective-box">
      <div class="obj-icon"><i class="fa-solid fa-microscope"></i></div>
      <h4>Empirical Auditing &amp; Verification</h4>
      <p>Developing mathematical auditing protocols based on Membership Inference Attacks (MIA) to empirically guarantee that deleted data cannot be reconstructed.</p>
    </div>

    <div class="objective-box">
      <div class="obj-icon"><i class="fa-solid fa-network-wired"></i></div>
      <h4>Architecture Scalability</h4>
      <p>Validating algorithmic efficiency across modern backbones including ResNets, Vision Transformers (ViTs), and multi-modal representation pipelines.</p>
    </div>
  </div>
</div>

<div class="serb-section-card">
  <h3><i class="fa-solid fa-timeline"></i> Phased Milestones &amp; Project Execution</h3>
  <p>
    With the full sanction and 100% disbursement of ₹30,50,300 INR, all project objectives and milestones were successfully executed and concluded on January 1, 2026:
  </p>

  <div class="serb-milestones">
    <div class="milestone-item">
      <span class="milestone-status status-done"><i class="fa-solid fa-check-circle"></i> Phase 1 &bull; Completed</span>
      <div class="milestone-content">
        <h4>Theoretical Framing &amp; Baseline Verification (Jan 2024 &ndash; Jun 2024)</h4>
        <p>Mathematical formalization of unlearning criteria; deployment of standard computer vision benchmark datasets; establishment of baseline Membership Inference auditing pipelines.</p>
      </div>
    </div>

    <div class="milestone-item">
      <span class="milestone-status status-done"><i class="fa-solid fa-check-circle"></i> Phase 2 &bull; Completed</span>
      <div class="milestone-content">
        <h4>Algorithm Development &amp; Parameter Scrubbing (Jul 2024 &ndash; Jun 2025)</h4>
        <p>Implementation of selective gradient inversion and localized Hessian approximations; extensive ablation on memory footprints and compute runtime reductions compared to standard retraining.</p>
      </div>
    </div>

    <div class="milestone-item">
      <span class="milestone-status status-done"><i class="fa-solid fa-check-circle"></i> Phase 3 &bull; Completed</span>
      <div class="milestone-content">
        <h4>Large-Scale Validation, Auditing Suite &amp; Dissemination (Jul 2025 &ndash; Jan 2026)</h4>
        <p>Benchmarking across vision-language architectures; development of empirical unlearning verification methodologies; publication dissemination and final SERB grant report submission.</p>
      </div>
    </div>
  </div>
</div>

<div class="serb-section-card">
  <h3><i class="fa-solid fa-users"></i> Research Personnel &amp; Laboratory</h3>
  <p>
    This project was conducted under the <strong>Responsible and Trustworthy Artificial Intelligence Lab</strong> at the School of Computer Applications, KIIT Deemed to be University:
  </p>

  <div class="serb-personnel-grid">
    <div class="serb-person-card">
      <div class="person-avatar">
        <i class="fa-solid fa-user-graduate"></i>
      </div>
      <div class="person-details">
        <h4>Dr. Murari Mandal</h4>
        <div class="person-role">Principal Investigator</div>
        <div class="person-affil">Associate Professor, KIIT Deemed to be University</div>
      </div>
    </div>

    <div class="serb-person-card">
      <div class="person-avatar">
        <i class="fa-solid fa-code"></i>
      </div>
      <div class="person-details">
        <h4>Umakanta Maharana</h4>
        <div class="person-role">Project Researcher</div>
        <div class="person-affil">Responsible AI, Vision &amp; Deep Learning</div>
      </div>
    </div>
  </div>
</div>

<div class="serb-section-card">
  <h3><i class="fa-solid fa-book-open"></i> Foundational Literature &amp; References</h3>
  <p>
    Key theoretical foundations and seminal literature informing the algorithmic development of this project:
  </p>

  <div class="serb-paper-card">
    <div class="paper-title">Towards Efficient Machine Unlearning</div>
    <div class="paper-meta">
      <span><i class="fa-solid fa-tag"></i> arXiv:2201.05629</span>
      <span>&bull;</span>
      <span>Machine Learning (cs.LG) &bull; Artificial Intelligence</span>
    </div>
    <div class="paper-actions">
      <a href="https://arxiv.org/abs/2201.05629" target="_blank" rel="noopener noreferrer" class="paper-btn">
        <i class="fa-solid fa-external-link"></i> Abstract
      </a>
      <a href="https://arxiv.org/pdf/2201.05629" target="_blank" rel="noopener noreferrer" class="paper-btn">
        <i class="fa-solid fa-file-pdf"></i> Download PDF
      </a>
    </div>
  </div>

  <div class="serb-paper-card">
    <div class="paper-title">Unlearning: A Key to the Selective Forgetting of Data in Deep Learning Models</div>
    <div class="paper-meta">
      <span><i class="fa-solid fa-tag"></i> arXiv:2210.08196</span>
      <span>&bull;</span>
      <span>Trustworthy AI &bull; Privacy-Preserving Neural Networks</span>
    </div>
    <div class="paper-actions">
      <a href="https://arxiv.org/abs/2210.08196" target="_blank" rel="noopener noreferrer" class="paper-btn">
        <i class="fa-solid fa-external-link"></i> Abstract
      </a>
      <a href="https://arxiv.org/pdf/2210.08196" target="_blank" rel="noopener noreferrer" class="paper-btn">
        <i class="fa-solid fa-file-pdf"></i> Download PDF
      </a>
    </div>
  </div>
</div>

<div class="serb-section-card" style="text-align: center; border-style: dashed;">
  <h3 style="justify-content: center;"><i class="fa-solid fa-handshake"></i> Academic Collaborations &amp; Inquiries</h3>
  <p style="text-align: center !important; max-width: 650px; margin: 0 auto 16px auto;">
    We welcome inquiries from academic researchers, students, and industry partners interested in machine unlearning, data privacy, and trustworthy AI.
  </p>
  <div style="display: flex; justify-content: center; gap: 12px; flex-wrap: wrap;">
    <a href="mailto:umakantamaharana1@gmail.com" class="quick-action-btn">
      <i class="fa-solid fa-envelope"></i> Contact Researchers
    </a>
    <a href="/projects/" class="quick-action-btn">
      <i class="fa-solid fa-diagram-project"></i> Explore Other Projects
    </a>
  </div>
</div>
