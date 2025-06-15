<style>
  .grant-bar-container {
    background: #254E58;
    border-radius: 8px;
    margin: 12px 0;
    padding: 10px 15px;
    color: #f7f9fa;
    font-family: Arial, sans-serif;
  }
  .grant-title {
    font-weight: 600;
    margin-bottom: 6px;
  }
  .progress-bar {
    background: #112D32;
    border-radius: 8px;
    height: 20px;
    position: relative;
    overflow: hidden;
  }
  .progress-fill {
    background: #02b8de;
    height: 100%;
    width: 0;
    border-radius: 8px 0 0 8px;
    transition: width 1.2s ease-in-out;
  }
  .grant-amount {
    margin-top: 6px;
    font-weight: 700;
  }
  .status {
    font-style: italic;
    color: #6E6658;
    margin-top: 4px;
  }
</style>

<div class="grant-bar-container" data-amount="2100000">
  <div class="grant-title">QMUK Research Capital Investment Fund - Functional Genomics Hub</div>
  <div class="progress-bar"><div class="progress-fill"></div></div>
  <div class="grant-amount">£2.1M (May 2025)</div>
  <div class="status">Awarded</div>
</div>

<div class="grant-bar-container" data-amount="4954">
  <div class="grant-title">Multi-Disciplinary Research Themes Pump Priming Award</div>
  <div class="progress-bar"><div class="progress-fill"></div></div>
  <div class="grant-amount">£4,954 (Nov 2022)</div>
  <div class="status">Awarded</div>
</div>

<div class="grant-bar-container" data-amount="806000">
  <div class="grant-title">BBSRC Mid-range Equipment Call (Pending)</div>
  <div class="progress-bar"><div class="progress-fill" style="background:#6E6658;"></div></div>
  <div class="grant-amount">£806K (Jan 2025)</div>
  <div class="status">Pending</div>
</div>

<script>
  document.querySelectorAll('.grant-bar-container').forEach(container => {
    const amount = parseFloat(container.getAttribute('data-amount'));
    // Using logarithmic scale for width between 5% and 95%
    const minWidth = 5;
    const maxWidth = 95;
    const minAmount = 1000; // set a floor to avoid log(0)
    const maxAmount = 2100000; // max grant amount
    
    const logMin = Math.log10(minAmount);
    const logMax = Math.log10(maxAmount);
    const logAmount = Math.log10(amount < minAmount ? minAmount : amount);
    
    const widthPercent = ((logAmount - logMin) / (logMax - logMin)) * (maxWidth - minWidth) + minWidth;
    const fill = container.querySelector('.progress-fill');
    fill.style.width = widthPercent + '%';
  });
</script>
