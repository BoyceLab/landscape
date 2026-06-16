# Submit an update

This is a living resource. If a record is wrong, out of date, or missing, you can fix it. Every submission is reviewed before it appears, so nothing posts automatically.

## The fastest way

Use the structured form on GitHub. It walks you through what to change and captures a source so the edit can be verified.

[Open the update form on GitHub](https://github.com/boycelab/landscape/issues/new?template=record-update.yml){ .md-button .md-button--primary target=_blank rel=noopener }

You will need a free GitHub account. If you do not have one, use the email option at the bottom of this page.

## Build a submission here

Prefer to stay on this page? Fill this in and it will open a pre-filled GitHub issue for you to post.

<div markdown="0">
<style>
.sb{display:grid;gap:10px;max-width:560px;margin:10px 0 4px}
.sb label{font-size:12px;letter-spacing:.08em;text-transform:uppercase;color:#6b7280;font-weight:700}
.sb input,.sb textarea{width:100%;padding:9px 11px;border:1px solid #e4dff0;border-radius:8px;font:inherit;font-size:14px}
.sb textarea{min-height:60px}
.sb button{background:#6d28d9;color:#fff;border:0;border-radius:9px;padding:10px 18px;font:inherit;font-weight:600;cursor:pointer;justify-self:start}
</style>
<div class="sb">
  <div><label>Gene or record</label><input id="u_gene" placeholder="e.g. SCN1A"></div>
  <div><label>What should change</label><input id="u_field" placeholder="e.g. Registry URL, foundation name, platform link"></div>
  <div><label>Correct value</label><textarea id="u_value" placeholder="The accurate information"></textarea></div>
  <div><label>Source (so we can verify)</label><input id="u_src" placeholder="A link or citation"></div>
  <div><label>Your contact (optional)</label><input id="u_contact" placeholder="email or org, if you want a reply"></div>
  <button onclick="buildIssue()">Open pre-filled submission →</button>
</div>
<script>
function buildIssue(){
  var REPO="boycelab/landscape";
  function v(id){return document.getElementById(id).value;}
  var body="### Record update\n\n- **Record:** "+(v('u_gene')||'(record)')+
    "\n- **Field to change:** "+(v('u_field')||'')+
    "\n- **Correct value:** "+(v('u_value')||'')+
    "\n- **Source:** "+(v('u_src')||'')+
    "\n- **Contact:** "+(v('u_contact')||'')+"\n";
  var url="https://github.com/"+REPO+"/issues/new?title="+
    encodeURIComponent("Record update: "+(v('u_gene')||''))+
    "&labels=record-update&body="+encodeURIComponent(body);
  window.open(url,"_blank","noopener");
}
</script>
</div>

## By email

No GitHub account and prefer email? Write to [danielle@boycedatascience.com](mailto:danielle@boycedatascience.com?subject=Atlas%20record%20update) with the record, the correct value, and a source.

!!! note "What makes a good submission"
    Tell us the record, the single field to change, the correct value, and where it comes from. A source link lets the change be verified and published quickly.
