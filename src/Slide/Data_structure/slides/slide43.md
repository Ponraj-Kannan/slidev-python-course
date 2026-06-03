<Slide2 topic="Real-World Use Cases — Part 2">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Real-World Use Cases — <span class="highlight">Part 2</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-orange">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-orange">Tuple</span>
      <div class="slide-h3" style="color:var(--orange);">GPS Coordinates</div>
    </div>
    <div class="body-text" style="margin-top:4px;">A pair like <span class="mono">(lat, lon)</span> — never changes for a given place.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">loc</span> = (<span style="color:#b45309;">13.0827</span>, <span style="color:#b45309;">80.2707</span>)
    </div>
  </div>

  <div v-click class="card card-green">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-green">Set</span>
      <div class="slide-h3" style="color:var(--green);">Tags on a Blog Post</div>
    </div>
    <div class="body-text" style="margin-top:4px;">Each tag is unique. Sets naturally prevent duplicates.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">tags</span> = {<span style="color:#2d7a00;">"python"</span>, <span style="color:#2d7a00;">"oops"</span>}
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-blue">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-blue">Dict</span>
      <div class="slide-h3" style="color:var(--blue);">JSON / API Responses</div>
    </div>
    <div class="body-text" style="margin-top:4px;">JSON maps directly to a nested dictionary in Python.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">data</span> = {<span style="color:#2d7a00;">"status"</span>:<span style="color:#2d7a00;">"ok"</span>, <span style="color:#2d7a00;">"id"</span>:<span style="color:#b45309;">7</span>}
    </div>
  </div>

  <div v-click class="card card-red">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-red">List</span>
      <div class="slide-h3" style="color:var(--red-dark);">Music Playlist</div>
    </div>
    <div class="body-text" style="margin-top:4px;">Songs in a fixed order, can add / remove / reorder.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">playlist</span>.<span style="color:#0e6ead;">insert</span>(<span style="color:#b45309;">0</span>, <span style="color:#2d7a00;">"intro"</span>)
    </div>
  </div>
</div>

</div>

<div v-click class="callout callout-success" style="margin-top:10px;">
  <div><strong>Rule of thumb:</strong> match the data's behaviour to the collection's strengths.</div>
</div>

  </template>
</Slide2>
