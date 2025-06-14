---
layout: page
title: Grants and Awards
---

<style>
  .grant-bar-container {
    background: #254E58;
    border-radius: 8px;
    margin: 16px 0;
    padding: 12px 16px;
    color: #f7f9fa;
    font-family: Arial, sans-serif;
  }

  .grant-title {
    font-weight: 600;
    margin-bottom: 6px;
    font-size: 1.05rem;
  }

  .progress-bar {
    background: #112D32;
    border-radius: 8px;
    height: 20px;
    overflow: hidden;
    margin-top: 4px;
  }

  .progress-fill {
    background: #02b8de;
    height: 100%;
    width: 0;
    border-radius: 8px 0 0 8px;
    transition: width 1.2s ease-in-out;
  }

  .progress-fill.pending {
    background: #6E6658;
  }

  .grant-amount {
    margin-top: 6px;
    font-weight: 700;
    font-size: 0.95rem;
  }

  .section-title {
    margin-top: 2rem;
    font-size: 1.3rem;
    color: #f7f9fa;
  }

  .award-box {
    background: #112D32;
    border: 1px solid #6E6658;
    border-radius: 8px;
    padding: 12px 16px;
    margin: 12px 0;
    color: #f7f9fa;
    font-size: 1rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .award-box i {
    color: #02b8de;
  }
</style>

### <span class="section-title">Funding</span>

<div class="grant-bar-container" data-amount="2100000">
  <div class="grant-title">QMUK Research Capital Investment Fund — <em>Functional Genomics Hub</em></div>
  <div class="progress-bar"><div class="progress-fill"></div></div>
  <div class="grant-amount">£2.1M (May 2025)</div>
</div>

<div class="grant-bar-container" data-amount="4954">
  <div class="grant-title">Multi-Disciplinary Research Themes Pump Priming Award</div>
  <div class="progress-bar"><div class="progress-fill"></div></div>
  <div class="grant-amount">£4,954 (Nov 2022)</div>
</div>

<div class="grant-bar-container" data-amount="27695">
  <div class="grant-title">The Medical College of Saint Bartholomew’s Hospital Trust</div>
  <div class="progress-bar"><div class="progress-fill"></div></div>
  <div class="grant-amount">£27,695 (Dec 2018)</div>
</div>

<div class="grant-bar-container" data-amount="1500">
  <div class="grant-title">Event Funding for Senescence Symposium</div>
  <div class="progress-bar"><div class="progress-fill"></div></div>
  <div class="grant-amount">£1,500 (Feb 2022)</div>
</div>

<div class="grant-bar-container" data-amount="2675">
  <div class="grant-title">Travel Awards for Conference Attendance</div>
  <div class="progress-bar"><div class="progress-fill"></div></div>
  <div class="grant-amount">£2,675 (Various)</div>
</div>

---

### <span class="section-title">Awards & Prizes</span>

<div class="award-box"><i class="fa-solid fa-trophy"></i> FMD Staff Awards Nomination – Outstanding Early Career Researcher (Sept 2022)</div>
<div class="award-box"><i class="fa-solid fa-medal"></i> 1st Poster Prize, London Inflammation Network (Sept 2018)</div>
<div class="award-box"><i class="fa-solid fa-medal"></i> 1st Poster Prize, Blizard Institute Graduate Studies Day (May 2018)</div>
<div class="award-box"><i class="fa-solid fa-chalkboard-user"></i> Selected abstracts / invited talks at 9 international/national conferences and symposia</div>

---

### <span class="section-title">Not Funded

<div class="grant-bar-container" data-amount="806000" data-pending>
  <div class="grant-title">BBSRC Mid-range Equipment Call (Co-lead)</div>
  <div class="progress-bar"><div class="progress-fill pending"></div></div>
  <div class="grant-amount">£806K (June 2025)</div>
</div>

<div class="grant-bar-container" data-amount="1200000" data-pending>
  <div class="grant-title">Wellcome Trust Early Career Fellowship</div>
  <div class="progress-bar"><div class="progress-fill pending"></div></div>
  <div class="grant-amount">£1.2M (Shortlisted for interview, Oct 2023)</div>
</div>

---

<script>
  document.querySelectorAll('.grant-bar-container').forEach(container => {
    const amount = parseFloat(container.getAttribute('data-amount'));
    const pending = container.hasAttribute('data-pending');
    const minAmount = 1000;
    const maxAmount = 2100000;

    const logMin = Math.log10(minAmount);
    const logMax = Math.log10(maxAmount);
    const logAmount = Math.log10(Math.max(minAmount, amount));

    const minWidth = 5;
    const maxWidth = 95;
    const width = ((logAmount - logMin) / (logMax - logMin)) * (maxWidth - minWidth) + minWidth;

    const fill = container.querySelector('.progress-fill');
    fill.style.width = width + "%";
    if (pending) {
      fill.classList.add("pending");
    }
  });
</script>

<!-- Font Awesome for icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
