---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 3 — WHAT IS A RECURSIVE FUNCTION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="What is a Recursive Function">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">What is a <span class="highlight">Recursive Function ?</span></div>

<div class="g2" style="gap:14px;">



<div class="flex-col">
  <div v-click class="section-label">Example — Sum of n Numbers</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># sum_n(3) = 3 + 2 + 1 = 6</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">sum_n</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># base case</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> + <span style="color:#0e6ead;">sum_n</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># recursive call</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">sum_n</span>(<span style="color:#b45309;">3</span>))
  </div>
</div>
<div class="flex-col">
<div v-click class="section-label" style="margin-top:6px;">How It Unfolds</div>

  <div style="display:flex;flex-direction:column;align-items:center;gap:3px;padding:6px 0;">
    <div class="flow-node flow-call" style="width:220px;" v-click>sum_n(3) = 3 + sum_n(2)</div>
    <div class="flow-arrow" v-after>&#x25BC;</div>
    <div class="flow-node flow-call" style="width:220px;" v-click>sum_n(2) = 2 + sum_n(1)</div>
    <div class="flow-arrow" v-after>&#x25BC;</div>
    <div class="flow-node flow-call" style="width:220px;" v-click>sum_n(1) = 1 + sum_n(0)</div>
    <div class="flow-arrow" v-after>&#x25BC;</div>
    <div class="flow-node flow-end" style="width:220px;" v-click>sum_n(0) = 0 (base case)</div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:4px;font-size:.7rem;  margin-bottom:40px;">
    <div>Each call <strong>waits</strong> for the next one to complete before returning its own result.</div>
  </div>
  </div>
</div>

  </template>
</Slide2>
