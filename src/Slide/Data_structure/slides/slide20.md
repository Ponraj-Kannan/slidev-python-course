<Slide2 topic="Tuple Access — Indexing &amp; Slicing">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Tuple <span class="highlight">Access</span> — Indexing &amp; Slicing</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Indexing (Positive &amp; Negative)</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">t</span> = (<span style="color:#2d7a00;">"a"</span>, <span style="color:#2d7a00;">"b"</span>, <span style="color:#2d7a00;">"c"</span>, <span style="color:#2d7a00;">"d"</span>)<br>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>[<span style="color:#b45309;">0</span>])    <span style="color:#6b7280;"># 'a'</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>[-<span style="color:#b45309;">1</span>])   <span style="color:#6b7280;"># 'd'</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>[<span style="color:#b45309;">2</span>])    <span style="color:#6b7280;"># 'c'</span>
  </div>

  <div v-click style="margin-top:4px;">
    <div class="section-label" style="margin-bottom:4px;">Index Map</div>
    <div style="display:flex;gap:4px;align-items:flex-start;">
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">a</div><div class="idx-num">0 / -4</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">b</div><div class="idx-num">1 / -3</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">c</div><div class="idx-num">2 / -2</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">d</div><div class="idx-num">3 / -1</div></div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Slicing</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">t</span> = (<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span>, <span style="color:#b45309;">40</span>, <span style="color:#b45309;">50</span>)<br>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>[<span style="color:#b45309;">1</span>:<span style="color:#b45309;">4</span>])  <span style="color:#6b7280;"># (20, 30, 40)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>[:<span style="color:#b45309;">2</span>])   <span style="color:#6b7280;"># (10, 20)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>[::-<span style="color:#b45309;">1</span>]) <span style="color:#6b7280;"># reverse</span>
  </div>

  <div v-click class="output-box" style="margin-top:4px;">
    (20, 30, 40)<br>
    (10, 20)<br>
    (50, 40, 30, 20, 10)
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div>Slicing a tuple returns a <strong>new tuple</strong> — the original is never changed.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
