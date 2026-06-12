# Research Readiness Self-Assessment

A short, honest read of where an organization stands across five tracks, with the specific support that moves it to the next stage and the option to connect with peer organizations at the same level. Answers stay in the browser unless the organization chooses to publish its level at the end.

<a href="../assets/self-assessment.html" target="_blank" rel="noopener" class="md-button md-button--primary dashboard-popout">
  ↗ Open in a new tab (recommended)
</a>

<div class="dashboard-wrapper">
  <button type="button" class="dashboard-fullscreen-btn" id="dashboard-fs-btn" title="Toggle fullscreen" aria-label="Toggle fullscreen">
    <span class="fs-icon-expand">⛶</span>
    <span class="fs-icon-collapse" style="display:none;">⛗</span>
    <span class="fs-label">Fullscreen</span>
  </button>
  <iframe id="dashboard-iframe" src="../assets/self-assessment.html" class="dashboard-frame" loading="lazy" title="Research Readiness Self-Assessment"></iframe>
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
