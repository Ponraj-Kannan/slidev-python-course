<Slide2 topic="Sets — Introduction">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Python <span class="highlight">Set</span> — Introduction</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">set</strong> is an <strong style="color:var(--green);">unordered</strong> collection of <strong style="color:var(--green);">unique</strong> values written between curly braces <span class="mono">{...}</span>.
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># Duplicates are removed automatically</span><br>
    <span style="color:#0e6ead;">s</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">3</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>)
  </div>

  <div v-click class="output-box">{1, 2, 3}</div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div>Sets are <strong>unordered</strong> — items have no fixed index, no slicing.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Use Cases</div>

  <div v-after class="card card-blue">
    <div class="slide-h3" style="margin-bottom:4px;">Unique Visitors</div>
    <div class="body-text">Track distinct user IDs on a website.</div>
  </div>

  <div v-click class="card card-orange">
    <div class="slide-h3" style="margin-bottom:4px;">Tags on a Post</div>
    <div class="body-text">Each tag only counts once.</div>
  </div>

  <div v-click class="card card-green">
    <div class="slide-h3" style="margin-bottom:4px;">Math Operations</div>
    <div class="body-text">Union, intersection, difference between groups.</div>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div>Sets are implemented with hashing — membership tests are very fast.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
