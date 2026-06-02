---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 5 — WHILE LOOP TRACING + INFINITE LOOP
═══════════════════════════════════════════════════════ -->

<Slide2 topic="While Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">While Loop — <span class="highlight">Tracing</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <!-- <div v-click class="section-label">Infinite while Loop — Danger Zone!</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.75rem;line-height:1.9;">
    <span style="color:#6b7280;"># Intentional infinite loop</span><br>
    <span style="color:#ef5050;">while</span> <span style="color:#c49a00;">True</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">user</span> = <span style="color:#2d7a00;">input</span>(<span style="color:#2d7a00;">"Enter 'quit' to stop: "</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">user</span> == <span style="color:#2d7a00;">"quit"</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">break</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"You said:"</span>, <span style="color:#0e6ead;">user</span>)</span>
  </div>
  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div><strong>while True:</strong> runs forever. Use <span class="mono" style="color:var(--red-dark);">break</span> to exit, or ensure the condition eventually becomes False.</div>
  </div>
  <div v-click class="card card-red" style="margin-top:4px;">
    <div class="small-text"><strong>Common mistake:</strong> Forgetting to update the counter variable inside the loop body.</div>
  </div> -->
  <div v-click class="section-label">Syntax Diagram</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px 18px;font-family:'Fira Code',monospace;font-size:.78rem;line-height:2;">
    <span style="color:#6b7280;"># Initialize variable</span><br>
    <span style="color:#0e6ead;">counter</span> = <span style="color:#b45309;">1</span><br>
    <br>
    <span style="color:#ef5050;">while</span> <span style="color:#0e6ead;">counter</span> <span style="color:#c49a00;">&lt;=</span> <span style="color:#b45309;">5</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">counter</span>)</span>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Update variable</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">counter</span> <span style="color:#c49a00;">+=</span> <span style="color:#b45309;">1</span></span>
  </div>
  <!-- <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    <span class="comment"># Output</span><br>
    1 &nbsp;2 &nbsp;3 &nbsp;4 &nbsp;5
  </div> -->
</div>
<div class="flex-col">
  <div v-after class="section-label">Step-by-Step Trace: counter = 1 to 5</div>
  <div>
    <table class="trace-table">
      <thead v-after  >
        <tr><th>Iteration</th><th>counter</th><th>Condition (counter &lt;= 5)</th><th>Output</th></tr>
      </thead>
      <tbody>
        <tr v-click><td>1</td><td>1</td><td class="yes">True</td><td>1</td></tr>
        <tr v-click><td>2</td><td>2</td><td class="yes">True</td><td>2</td></tr>
        <tr v-click><td>3</td><td>3</td><td class="yes">True</td><td>3</td></tr>
        <tr v-click><td>4</td><td>4</td><td class="yes">True</td><td>4</td></tr>
        <tr v-click><td>5</td><td>5</td><td class="yes">True</td><td>5</td></tr>
        <tr v-click class="hl"><td>6</td><td>6</td><td class="no">False</td><td>Exit</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    <span class="comment"># Output</span><br>
    1 &nbsp;2 &nbsp;3 &nbsp;4 &nbsp;5
  </div>
</div>

</div>

  </template>
</Slide2>
