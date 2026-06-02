---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 10 — while vs for COMPARISON
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Comparison">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">while</span> Loop vs <span class="highlight">for</span> Loop</div>

<div >
<table class="cmp-table">
  <thead>
    <tr>
      <th>Feature</th>
      <th>while Loop</th>
      <th>for Loop</th>
    </tr>
  </thead>
  <tbody>
    <tr v-click>
      <td><strong>Use when</strong></td>
      <td>Number of iterations is <strong>unknown</strong></td>
      <td>Number of iterations is <strong>known</strong></td>
    </tr>
    <tr v-click>
      <td><strong>Condition</strong></td>
      <td>Custom boolean condition</td>
      <td>Iterates over a sequence</td>
    </tr>
    <tr v-click>
      <td><strong>Counter update</strong></td>
      <td class="no">Manual — must do it yourself</td>
      <td class="yes">Automatic</td>
    </tr>
    <tr v-click>
      <td><strong>Risk of infinite loop</strong></td>
      <td class="no">Higher (if update is missed)</td>
      <td class="yes">Lower</td>
    </tr>
    <tr v-click>
      <td><strong>Typical use case</strong></td>
      <td>Menu-driven programs, user input</td>
      <td>Traversing lists, strings, ranges</td>
    </tr>
  </tbody>
</table>
</div>

<div class="g2" style="gap:10px;margin-top:12px;">

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <div style="color:#ef5050;font-weight:700;margin-bottom:6px;">while loop</div>
    <span style="color:#0e6ead;">i</span> = <span style="color:#b45309;">1</span><br>
    <span style="color:#ef5050;">while</span> <span style="color:#0e6ead;">i</span> &lt;= <span style="color:#b45309;">5</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">i</span> += <span style="color:#b45309;">1</span></span>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <div style="color:#2d7a00;font-weight:700;margin-bottom:6px;">for loop — same result, less code</div>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
  </div>

</div>

  </template>
</Slide2>
