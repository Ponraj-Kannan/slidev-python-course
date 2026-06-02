---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 11 — DIRECT RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Direct Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Direct</span> Recursion</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.7;color:var(--slate);">
      <strong style="color:var(--red);">Direct recursion</strong> occurs when a function <strong style="color:var(--green);">calls itself directly</strong> within its own body. This is the most common and simplest form of recursion.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Flow Diagram — Direct</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;padding:8px 0;">
    <div class="flow-node flow-start" style="width:200px;">func_A called</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-body" style="width:200px;">executes body...</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-call" style="width:200px;">calls func_A again</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-cond" style="width:200px;">base case reached?</div>
    <div style="display:flex;gap:20px;margin-top:4px;">
      <div style="display:flex;flex-direction:column;align-items:center;gap:2px;">
        <div class="small-text">YES</div>
        <div class="flow-node flow-end" style="width:100px;">return</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;gap:2px;">
        <div class="small-text">NO</div>
        <div class="flow-node flow-call" style="width:100px;">recurse</div>
      </div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 1 — Countdown</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">countdown</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> &lt; <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">countdown</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># calls itself!</span></span>
    <br>
    <span style="color:#0e6ead;">countdown</span>(<span style="color:#b45309;">3</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">3 &nbsp; 2 &nbsp; 1 &nbsp; 0</div>

  <div v-click class="section-label" style="margin-top:6px;">Example 2 — Sum of Digits</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">digit_sum</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> % <span style="color:#b45309;">10</span> + <span style="color:#0e6ead;">digit_sum</span>(<span style="color:#0e6ead;">n</span> // <span style="color:#b45309;">10</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">digit_sum</span>(<span style="color:#b45309;">123</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">6 &nbsp;<span class="comment"># 1 + 2 + 3 = 6</span></div>

  <div v-click class="callout callout-success" style="font-size:.7rem; margin-bottom:40px;">
    <div><strong>Direct recursion</strong> is clean and easy to trace — the function only depends on itself.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
