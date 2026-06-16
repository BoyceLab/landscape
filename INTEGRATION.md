# Lessons learned

The hardest won knowledge in this community is what to avoid. This is a place for organizations to report what did not work in their research experience, and what they would do differently, so the next group at the same stage does not repeat it.

It is built around one principle: **fit, not fault.** Most lessons are a mismatch between an approach and where an organization was at the time, not wrongdoing by anyone. Submissions are framed as your own experience and advice, anchored to your stage in the [maturity model](maturity-model.md).

!!! note "How submissions are handled"
    Nothing publishes automatically. A reviewer removes names, personal health information, and any phrasing that reads as a factual charge against a third party, then publishes the lesson as your account. Organizations stay anonymous unless they choose to be named.

!!! warning "What this is, and is not"
    Published lessons are individual organizations' experiences and opinions. They are not verified statements of fact about any product, organization, or person, and they are not endorsements. Describe approaches and partners by category rather than name. If a specific entity is named, it must be plain verifiable fact, it receives stricter review, and the named party has a right of reply and correction. To raise a concern about a published lesson, write to [danielle@boycedatascience.com](mailto:danielle@boycedatascience.com?subject=Lessons%20learned%20concern).

<a href="../assets/lessons.html" target="_blank" rel="noopener" class="md-button md-button--primary dashboard-popout">
  ↗ Open in a new tab (recommended)
</a>

<div class="dashboard-wrapper">
  <button type="button" class="dashboard-fullscreen-btn" id="dashboard-fs-btn" title="Toggle fullscreen" aria-label="Toggle fullscreen">
    <span class="fs-icon-expand">⛶</span>
    <span class="fs-icon-collapse" style="display:none;">⛗</span>
    <span class="fs-label">Fullscreen</span>
  </button>
  <iframe id="dashboard-iframe" src="../assets/lessons.html" class="dashboard-frame" loading="lazy" title="Lessons learned"></iframe>
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
