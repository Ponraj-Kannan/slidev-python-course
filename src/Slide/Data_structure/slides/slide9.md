<Slide2 topic="Lists — Slicing">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">List <span class="highlight">Slicing</span> — <span class="mono">list[start:stop:step]</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Slicing Examples</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span>, <span style="color:#b45309;">40</span>, <span style="color:#b45309;">50</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>[<span style="color:#b45309;">1</span>:<span style="color:#b45309;">4</span>])    <span style="color:#6b7280;"># [20,30,40]</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>[:<span style="color:#b45309;">3</span>])     <span style="color:#6b7280;"># [10,20,30]</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>[<span style="color:#b45309;">2</span>:])     <span style="color:#6b7280;"># [30,40,50]</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>[::<span style="color:#b45309;">2</span>])    <span style="color:#6b7280;"># [10,30,50]</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>[::-<span style="color:#b45309;">1</span>])   <span style="color:#6b7280;"># reverse</span>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><strong>Stop</strong> is exclusive — the index at <span class="mono">stop</span> is NOT included in the slice.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Visual: n[1:4]</div>

  <div v-after style="background:#f7f8fc;padding:10px;border-radius:10px;border:1px solid var(--border);">
    <div style="display:flex;gap:4px;align-items:flex-start;justify-content:center;">
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">10</div><div class="idx-num">0</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell hl">20</div><div class="idx-num">1</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell hl">30</div><div class="idx-num">2</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell hl">40</div><div class="idx-num">3</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">50</div><div class="idx-num">4</div></div>
    </div>
    <div class="small-text" style="text-align:center;margin-top:6px;">Highlighted = part of <span class="mono">n[1:4]</span></div>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:4px;">Cheat Sheet</div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead><tr><th>Slice</th><th>Meaning</th></tr></thead>
      <tbody>
        <tr><td class="mono">n[:]</td><td>copy of full list</td></tr>
        <tr><td class="mono">n[::-1]</td><td>reverse the list</td></tr>
        <tr><td class="mono">n[-3:]</td><td>last 3 items</td></tr>
        <tr><td class="mono">n[:-2]</td><td>all except last 2</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

  </template>
</Slide2>
