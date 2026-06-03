<Slide2 topic="Dictionary Recap">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Dictionary — <span class="highlight">Recap</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-blue">
    <div class="slide-h3" style="margin-bottom:6px;">Why Dicts?</div>
    <div class="body-text">Map a meaningful label to a value — far more readable than parallel lists.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#6b7280;"># Awkward — two parallel lists</span><br>
    <span style="color:#0e6ead;">names</span> = [<span style="color:#2d7a00;">"Anu"</span>, <span style="color:#2d7a00;">"Ravi"</span>]<br>
    <span style="color:#0e6ead;">ages</span>  = [<span style="color:#b45309;">19</span>, <span style="color:#b45309;">20</span>]<br>
    <span style="color:#6b7280;"># Index must match!</span><br>
    <br>
    <span style="color:#6b7280;"># Clean — one dict</span><br>
    <span style="color:#0e6ead;">people</span> = {<span style="color:#2d7a00;">"Anu"</span>: <span style="color:#b45309;">19</span>, <span style="color:#2d7a00;">"Ravi"</span>: <span style="color:#b45309;">20</span>}
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Quick Cheat Sheet</div>

  <div v-after class="card-navy" style="border-radius:10px;padding:14px;">
    <div style="font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.8;">
      <div>d = {} <span style="color:var(--muted);"># empty</span></div>
      <div>d["key"] = value <span style="color:var(--muted);"># add/update</span></div>
      <div>d.get("key", default) <span style="color:var(--muted);"># safe read</span></div>
      <div>d.keys() / d.values() / d.items()</div>
      <div>d.pop("key") <span style="color:var(--muted);"># remove</span></div>
      <div>for k, v in d.items():</div>
      <div>&nbsp;&nbsp;&nbsp;&nbsp;process(k, v)</div>
    </div>
  </div>

  <div v-click class="callout callout-success">
    <div><strong>Pick a dict when</strong> your data has a meaningful name -> value mapping.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
