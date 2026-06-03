<Slide2 topic="Dictionary Features &amp; Creation">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Dict <span class="highlight">Features</span> &amp; <span class="highlight">Creating</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Features</div>

  <div v-after class="card" style="display:flex;gap:10px;align-items:center;">
    <div class="icon-circle ic-red">K</div>
    <div>
      <div class="slide-h3">Unique Keys</div>
      <div class="small-text">Each key appears only once. Re-assigning overwrites.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;">
    <div class="icon-circle ic-blue">M</div>
    <div>
      <div class="slide-h3">Mutable</div>
      <div class="small-text">Add, change, or delete entries any time.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;">
    <div class="icon-circle ic-green">O</div>
    <div>
      <div class="slide-h3">Ordered (Python 3.7+)</div>
      <div class="small-text">Items keep their insertion order.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;">
    <div class="icon-circle ic-orange">F</div>
    <div>
      <div class="slide-h3">Fast Lookup</div>
      <div class="small-text">Hashed keys -> near-instant access by key.</div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Creating Dictionaries</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Empty dict</span><br>
    <span style="color:#0e6ead;">a</span> = {}<br>
    <br>
    <span style="color:#6b7280;"># Literal</span><br>
    <span style="color:#0e6ead;">b</span> = {<span style="color:#2d7a00;">"a"</span>: <span style="color:#b45309;">1</span>, <span style="color:#2d7a00;">"b"</span>: <span style="color:#b45309;">2</span>}<br>
    <br>
    <span style="color:#6b7280;"># dict() constructor</span><br>
    <span style="color:#0e6ead;">c</span> = <span style="color:#2d7a00;">dict</span>(<span style="color:#0e6ead;">name</span>=<span style="color:#2d7a00;">"Anu"</span>, <span style="color:#0e6ead;">age</span>=<span style="color:#b45309;">19</span>)<br>
    <br>
    <span style="color:#6b7280;"># From pairs</span><br>
    <span style="color:#0e6ead;">d</span> = <span style="color:#2d7a00;">dict</span>([(<span style="color:#2d7a00;">"x"</span>,<span style="color:#b45309;">1</span>), (<span style="color:#2d7a00;">"y"</span>,<span style="color:#b45309;">2</span>)])
  </div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div><span class="mono">{}</span> creates an empty <strong>dict</strong>, not a set. Use <span class="mono">set()</span> for an empty set.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
