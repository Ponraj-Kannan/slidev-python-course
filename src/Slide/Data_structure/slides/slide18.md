<Slide2 topic="Features of Tuples">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Features of a <span class="highlight">Tuple</span></div>

<div class="g3" style="gap:10px;">

  <div v-click class="card card-red" style="text-align:center;">
    <div class="icon-circle ic-red" style="margin:0 auto 6px;">O</div>
    <div class="slide-h3" style="color:var(--red-dark);">Ordered</div>
    <div class="small-text" style="margin-top:4px;">Items have a fixed position.</div>
  </div>

  <div v-click class="card card-orange" style="text-align:center;">
    <div class="icon-circle ic-orange" style="margin:0 auto 6px;">I</div>
    <div class="slide-h3" style="color:var(--orange);">Immutable</div>
    <div class="small-text" style="margin-top:4px;">Cannot be modified once created.</div>
  </div>

  <div v-click class="card card-green" style="text-align:center;">
    <div class="icon-circle ic-green" style="margin:0 auto 6px;">D</div>
    <div class="slide-h3" style="color:var(--green);">Duplicates OK</div>
    <div class="small-text" style="margin-top:4px;">The same value can appear many times.</div>
  </div>

</div>

<div v-click style="margin-top:12px;">
  <div class="section-label" style="margin-bottom:6px;">Immutability in Action</div>
  <div class="g2" style="gap:10px;">
    <div class="code-block">
      <span style="color:#6b7280;"># OK — reading is fine</span><br>
      <span style="color:#0e6ead;">t</span> = (<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>)<br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">t</span>[<span style="color:#b45309;">0</span>])  <span style="color:#6b7280;"># 1</span>
    </div>
    <div class="code-block" style="border-color:var(--red);">
      <span style="color:#6b7280;"># Error — writing not allowed</span><br>
      <span style="color:#0e6ead;">t</span>[<span style="color:#b45309;">0</span>] = <span style="color:#b45309;">99</span><br>
      <span style="color:#c0392b;font-weight:700;"># TypeError</span>
    </div>
  </div>
</div>

<div v-click class="callout callout-warn" style="margin-top:8px;">
  <div><strong>Trade-off:</strong> Immutability brings safety and speed, but you cannot grow or shrink a tuple.</div>
</div>

  </template>
</Slide2>
