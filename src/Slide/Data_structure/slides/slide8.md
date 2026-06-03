<Slide2 topic="Lists — Indexing">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Accessing List Elements — <span class="highlight">Indexing</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Positive Indexing</div>
    <div class="small-text" style="margin-top:4px;">Starts at <strong>0</strong> from the left.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">fruits</span> = [<span style="color:#2d7a00;">"apple"</span>, <span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"cherry"</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fruits</span>[<span style="color:#b45309;">0</span>])  <span style="color:#6b7280;"># apple</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fruits</span>[<span style="color:#b45309;">2</span>])  <span style="color:#6b7280;"># cherry</span>
  </div>

  <div v-click style="margin-top:4px;">
    <div class="section-label" style="margin-bottom:4px;">Positive Index View</div>
    <div style="display:flex;gap:4px;align-items:flex-start;">
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell hl">apple</div><div class="idx-num">0</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">banana</div><div class="idx-num">1</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">cherry</div><div class="idx-num">2</div></div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-orange" style="text-align:center;">
    <div class="slide-h2" style="color:var(--orange);">Negative Indexing</div>
    <div class="small-text" style="margin-top:4px;">Starts at <strong>-1</strong> from the right (last item).</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">fruits</span> = [<span style="color:#2d7a00;">"apple"</span>, <span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"cherry"</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fruits</span>[-<span style="color:#b45309;">1</span>])  <span style="color:#6b7280;"># cherry</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fruits</span>[-<span style="color:#b45309;">3</span>])  <span style="color:#6b7280;"># apple</span>
  </div>

  <div v-click style="margin-top:4px;">
    <div class="section-label" style="margin-bottom:4px;">Negative Index View</div>
    <div style="display:flex;gap:4px;align-items:flex-start;">
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">apple</div><div class="idx-num">-3</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell">banana</div><div class="idx-num">-2</div></div>
      <div style="display:flex;flex-direction:column;align-items:center;"><div class="idx-cell hl">cherry</div><div class="idx-num">-1</div></div>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="font-size:.7rem;margin-top:6px;">
    <div>Out-of-range index causes an <strong>IndexError</strong>.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
