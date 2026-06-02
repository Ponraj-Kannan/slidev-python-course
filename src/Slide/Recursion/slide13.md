---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — TAIL RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Tail Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Tail</span> Recursion</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.7;color:var(--slate);">
      A function is <strong style="color:var(--red);">tail recursive</strong> when the <strong style="color:var(--green);">recursive call is the last operation</strong> in the function — no pending computation after it returns.
    </div>
  </div>

  <div v-click class="g2" style="gap:8px;margin-top:4px;">
    <div class="card-red">
      <div class="slide-h3">NOT Tail Recursive</div>
      <div class="small-text" style="margin-top:4px;">There is a pending multiply after the call returns.</div>
    </div>
    <div class="card-green">
      <div class="slide-h3">Tail Recursive</div>
      <div class="small-text" style="margin-top:4px;">The recursive call IS the last thing done — nothing pending.</div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">NOT Tail Recursive (standard factorial)</div>

  <div v-after class="code-block" style="font-size:.7rem;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>: <span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
    <span style="color:#6b7280;">#       ^ must multiply after call returns</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Tail Recursive Version</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Tail recursive — accumulator carries result</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>, <span style="color:#0e6ead;">acc</span>=<span style="color:#b45309;">1</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">acc</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>, <span style="color:#0e6ead;">n</span>*<span style="color:#0e6ead;">acc</span>) <span style="color:#6b7280;"># LAST op</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">factorial</span>(<span style="color:#b45309;">5</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">120</div>

  <div v-click class="section-label" style="margin-top:6px;">Comparison</div>
  <div v-after>
    <table class="cmp-table">
      <thead><tr><th>Aspect</th><th>Normal Recursion</th><th>Tail Recursion</th></tr></thead>
      <tbody>
        <tr><td>Pending operation</td><td class="no">Yes (e.g. n*...)</td><td class="yes">None</td></tr>
        <tr><td>Stack frames</td><td class="no">All kept alive</td><td class="yes">Can be reused</td></tr>
        <tr><td>Memory</td><td class="no">O(n)</td><td class="yes">O(1) if optimized</td></tr>
        <tr><td>Accumulator needed</td><td>No</td><td>Yes</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem; margin-bottom:40px;">
    <div><strong>Note:</strong> Python does not optimize tail recursion automatically, but the pattern is still a good practice for clarity.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
