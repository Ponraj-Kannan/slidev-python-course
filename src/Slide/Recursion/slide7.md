---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — RECURSIVE FLOW EXECUTION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Recursive Flow — Step-by-Step Execution">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Recursive <span class="highlight">Flow Execution</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example — Reverse a String</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">reverse</span>(<span style="color:#0e6ead;">s</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">s</span>) == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># base case</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">""</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">reverse</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">1</span>:]) + <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>]</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">reverse</span>(<span style="color:#2d7a00;">"ABC"</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">CBA</div>

  <div v-click class="section-label" style="margin-top:6px;">Execution Trace Table</div>

  <div v-after>
    <table class="trace-table">
      <thead><tr><th>Call</th><th>Input s</th><th>Action</th><th>Returns</th></tr></thead>
      <tbody>
        <tr><td>1st</td><td>"ABC"</td><td>reverse("BC") + "A"</td><td>waits</td></tr>
        <tr><td>2nd</td><td>"BC"</td><td>reverse("C") + "B"</td><td>waits</td></tr>
        <tr><td>3rd</td><td>"C"</td><td>reverse("") + "C"</td><td>waits</td></tr>
        <tr class="hl"><td>4th</td><td>""</td><td>base case</td><td class="hl">""</td></tr>
        <tr><td>3rd</td><td>unwind</td><td>"" + "C"</td><td>"C"</td></tr>
        <tr><td>2nd</td><td>unwind</td><td>"C" + "B"</td><td>"CB"</td></tr>
        <tr><td>1st</td><td>unwind</td><td>"CB" + "A"</td><td class="hl">"CBA"</td></tr>
      </tbody>
    </table>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Complete Execution Flow Diagram</div>

  <div style="display:flex;flex-direction:column;align-items:center;gap:3px;padding:4px 0;">
    <div class="flow-node flow-start" style="width:240px;" v-click>reverse("ABC")</div>
    <div class="flow-arrow" v-after>&#x25BC;</div>
    <div class="flow-node flow-call" style="width:240px;" v-click>reverse("BC") + "A"</div>
    <div class="flow-arrow" v-after>&#x25BC;</div>
    <div class="flow-node flow-call" style="width:240px;" v-click>reverse("C") + "B"</div>
    <div class="flow-arrow" v-after>&#x25BC;</div>
    <div class="flow-node flow-call" style="width:240px;" v-click>reverse("") + "C"</div>
    <div class="flow-arrow" v-after>&#x25BC;</div>
    <div class="flow-node flow-end" style="width:240px;" v-click>returns "" (base case)</div>
    <div class="flow-arrow" v-after>&#x25B2;</div>
    <div class="flow-node flow-return" style="width:240px;" v-click>returns "C"</div>
    <div class="flow-arrow" v-after>&#x25B2;</div>
    <div class="flow-node flow-return" style="width:240px;" v-click>returns "CB"</div>
    <div class="flow-arrow" v-after>&#x25B2;</div>
    <div class="flow-node flow-body" style="width:240px;" v-click>returns "CBA"</div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;font-size:.7rem;  margin-bottom:40px;">
    <div>The recursive calls go <strong>down</strong> until base case, then results are <strong>assembled on the way back up</strong>.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
