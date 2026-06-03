<Slide2 topic="Features of Sets">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Features of a <span class="highlight">Set</span></div>

<div class="g3" style="gap:10px;">

  <div v-click class="card card-red" style="text-align:center;">
    <div class="icon-circle ic-red" style="margin:0 auto 6px;">U</div>
    <div class="slide-h3" style="color:var(--red-dark);">Unordered</div>
    <div class="small-text" style="margin-top:4px;">Items have no position or index.</div>
  </div>

  <div v-click class="card card-blue" style="text-align:center;">
    <div class="icon-circle ic-blue" style="margin:0 auto 6px;">M</div>
    <div class="slide-h3" style="color:var(--blue);">Mutable</div>
    <div class="small-text" style="margin-top:4px;">Add or remove items at any time.</div>
  </div>

  <div v-click class="card card-green" style="text-align:center;">
    <div class="icon-circle ic-green" style="margin:0 auto 6px;">Q</div>
    <div class="slide-h3" style="color:var(--green);">Unique only</div>
    <div class="small-text" style="margin-top:4px;">Duplicates are silently dropped.</div>
  </div>

</div>

<div v-click class="callout callout-danger" style="margin-top:10px;">
  <div><strong>Important:</strong> items inside a set must be <strong>hashable</strong> (immutable). You cannot put a list inside a set, but a tuple is fine.</div>
</div>

<div v-click style="margin-top:8px;">
  <div class="section-label" style="margin-bottom:6px;">Order vs No-Order</div>
  <div class="g2" style="gap:10px;">
    <div class="code-block">
      <span style="color:#6b7280;"># Order matters in a list</span><br>
      <span style="color:#2d7a00;">print</span>([<span style="color:#b45309;">1</span>,<span style="color:#b45309;">2</span>,<span style="color:#b45309;">3</span>] == [<span style="color:#b45309;">3</span>,<span style="color:#b45309;">2</span>,<span style="color:#b45309;">1</span>])<br>
      <span style="color:#6b7280;"># False</span>
    </div>
    <div class="code-block">
      <span style="color:#6b7280;"># Order is irrelevant in a set</span><br>
      <span style="color:#2d7a00;">print</span>({<span style="color:#b45309;">1</span>,<span style="color:#b45309;">2</span>,<span style="color:#b45309;">3</span>} == {<span style="color:#b45309;">3</span>,<span style="color:#b45309;">2</span>,<span style="color:#b45309;">1</span>})<br>
      <span style="color:#6b7280;"># True</span>
    </div>
  </div>
</div>

  </template>
</Slide2>
