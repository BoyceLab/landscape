# Async user testing

Self-guided testing that a participant completes on their own time, with no facilitator. Testers pick the role that fits them, work through a few short tasks in the Atlas, and submit structured feedback by copying it, downloading it, or opening a pre-filled GitHub submission. See the [testing overview](index.md) for the facilitated protocol.

<a href="../assets/user-testing.html" target="_blank" rel="noopener" class="md-button md-button--primary dashboard-popout">
  ↗ Open in a new tab (recommended)
</a>

<div class="dashboard-wrapper">
  <button type="button" class="dashboard-fullscreen-btn" id="dashboard-fs-btn" title="Toggle fullscreen" aria-label="Toggle fullscreen">
    <span class="fs-icon-expand">⛶</span>
    <span class="fs-icon-collapse" style="display:none;">⛗</span>
    <span class="fs-label">Fullscreen</span>
  </button>
  <iframe id="dashboard-iframe" src="../assets/user-testing.html" class="dashboard-frame" loading="lazy" title="Async user testing"></iframe>
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
