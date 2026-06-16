# Reports and lists

Build a filtered list of genes or organizations and take it with you. Narrow by inheritance, phenotype, what infrastructure exists, whether the gene is in the network layer, indicative level, or community, then export the result as CSV, copy it as a table into a spreadsheet or a document, or print it to PDF. The active filters travel with the export, so any list documents how it was made.

<a href="../assets/report.html" target="_blank" rel="noopener" class="md-button md-button--primary dashboard-popout">
  ↗ Open in a new tab (recommended)
</a>

<div class="dashboard-wrapper">
  <button type="button" class="dashboard-fullscreen-btn" id="dashboard-fs-btn" title="Toggle fullscreen" aria-label="Toggle fullscreen">
    <span class="fs-icon-expand">⛶</span>
    <span class="fs-icon-collapse" style="display:none;">⛗</span>
    <span class="fs-label">Fullscreen</span>
  </button>
  <iframe id="dashboard-iframe" src="../assets/report.html" class="dashboard-frame" loading="lazy" title="Report builder"></iframe>
</div>

<script>
(function() {
  var btn = document.getElementById('dashboard-fs-btn');
  var wrapper = document.querySelector('.dashboard-wrapper');
  var expand = btn.querySelector('.fs-icon-expand');
  var collapse = btn.querySelector('.fs-icon-collapse');
  var label = btn.querySelector('.fs-label');
  function inFs(){return document.fullscreenElement||document.webkitFullscreenElement;}
  btn.addEventListener('click',function(){
    if(inFs()){(document.exitFullscreen||document.webkitExitFullscreen).call(document);}
    else{var r=wrapper.requestFullscreen||wrapper.webkitRequestFullscreen;if(r)r.call(wrapper);}});
  function sync(){if(inFs()){expand.style.display='none';collapse.style.display='';label.textContent='Exit fullscreen';}
    else{expand.style.display='';collapse.style.display='none';label.textContent='Fullscreen';}}
  document.addEventListener('fullscreenchange',sync);
  document.addEventListener('webkitfullscreenchange',sync);
})();
</script>
