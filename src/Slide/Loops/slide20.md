---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — else WITH LOOPS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="else with Loops">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">else</span> with Loops — Python's Unique Feature</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      The <strong style="color:var(--red);">else</strong> block after a loop runs <strong style="color:var(--green);">only when the loop completes normally</strong> — i.e., when the condition becomes False naturally, <strong>not</strong> when broken by <span class="mono" style="color:var(--red-dark);">break</span>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:6px;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Loop finished normally!"</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5<br>
    <span style="color:#b45309;">Loop finished normally!</span>
  </div>
</div>

<div class="flex-col">
  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#6b7280;"># break prevents else from running</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">i</span> == <span style="color:#b45309;">3</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">break</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"This won't print!"</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 2 &nbsp; <span style="color:#c0392b;">(stopped by break — else skipped)</span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">When does else run?</div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead><tr><th>Loop ends via</th><th>else runs?</th></tr></thead>
      <tbody>
        <tr><td>Condition became False (normal)</td><td class="yes">Yes</td></tr>
        <tr><td>Sequence exhausted (for loop)</td><td class="yes">Yes</td></tr>
        <tr><td>break statement</td><td class="no">No</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div><strong>Use case:</strong> Search loops — run else when item is NOT found after exhausting all elements.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
