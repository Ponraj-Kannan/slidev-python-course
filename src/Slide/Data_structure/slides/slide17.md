<Slide2 topic="Tuples — Introduction">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Python <span class="highlight">Tuple</span> — Introduction</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">tuple</strong> is an <strong style="color:var(--green);">ordered, immutable</strong> collection written between parentheses <span class="mono">(...)</span>.
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># A simple tuple</span><br>
    <span style="color:#0e6ead;">point</span> = (<span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">point</span>)
  </div>

  <div v-click class="output-box">(10, 20)</div>

  <div v-click class="callout callout-danger" style="font-size:.7rem;">
    <div>Tuples are <strong>immutable</strong> — you cannot change items after creation.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Use Cases</div>

  <div v-after class="card card-blue">
    <div class="slide-h3" style="margin-bottom:4px;">Coordinates</div>
    <div class="body-text">A fixed pair like <span class="mono">(latitude, longitude)</span>.</div>
  </div>

  <div v-click class="card card-orange">
    <div class="slide-h3" style="margin-bottom:4px;">Fixed Records</div>
    <div class="body-text">An RGB color: <span class="mono">(255, 100, 0)</span>.</div>
  </div>

  <div v-click class="card card-green">
    <div class="slide-h3" style="margin-bottom:4px;">Function Return</div>
    <div class="body-text">A function returning multiple values returns a tuple.</div>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div>Tuples are slightly <strong>faster</strong> and use <strong>less memory</strong> than lists.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
