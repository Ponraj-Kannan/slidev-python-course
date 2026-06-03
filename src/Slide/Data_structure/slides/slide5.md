<Slide2 topic="Lists — Introduction">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Python <span class="highlight">List</span> — Introduction</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">list</strong> is an <strong style="color:var(--green);">ordered, mutable</strong> collection of items written between square brackets <span class="mono">[...]</span>.
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># A simple list of integers</span><br>
    <span style="color:#0e6ead;">marks</span> = [<span style="color:#b45309;">82</span>, <span style="color:#b45309;">76</span>, <span style="color:#b45309;">91</span>, <span style="color:#b45309;">88</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">marks</span>)
  </div>

  <div v-click class="output-box">[82, 76, 91, 88]</div>

  <div v-click class="callout callout-info">
    <div>Lists can hold <strong>any data type</strong>: numbers, strings, even other lists.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Memory View</div>

  <div v-after style="display:flex;flex-direction:column;gap:6px;background:#f7f8fc;padding:12px;border-radius:10px;border:1px solid var(--border);">
    <div style="font-size:.7rem;color:var(--muted);">marks =</div>
    <div style="display:flex;gap:4px;align-items:flex-start;">
      <div style="display:flex;flex-direction:column;align-items:center;">
        <div class="idx-cell">82</div>
        <div class="idx-num">0</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;">
        <div class="idx-cell">76</div>
        <div class="idx-num">1</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;">
        <div class="idx-cell">91</div>
        <div class="idx-num">2</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;">
        <div class="idx-cell">88</div>
        <div class="idx-num">3</div>
      </div>
    </div>
    <div style="font-size:.62rem;color:var(--muted);">Index always starts at 0.</div>
  </div>

  <div v-click class="card card-green" style="margin-top:6px;">
    <div class="small-text"><strong>Use a list when:</strong> the order matters and values may change.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
