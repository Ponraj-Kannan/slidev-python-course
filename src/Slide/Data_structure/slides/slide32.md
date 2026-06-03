<Slide2 topic="Dictionaries — Introduction">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Python <span class="highlight">Dictionary</span> — Introduction</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">dictionary</strong> stores data as <strong style="color:var(--green);">key : value</strong> pairs — perfect for mapping a label to a value.
    </div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">student</span> = {<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"name"</span>: <span style="color:#2d7a00;">"Anu"</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"age"</span>: <span style="color:#b45309;">19</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"cgpa"</span>: <span style="color:#b45309;">8.5</span></span>
    }<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">student</span>[<span style="color:#2d7a00;">"name"</span>])
  </div>

  <div v-click class="output-box">Anu</div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Key-Value Diagram</div>

  <div v-after style="display:flex;flex-direction:column;gap:6px;background:#f7f8fc;padding:12px;border-radius:10px;border:1px solid var(--border);">
    <div class="kv-row"><span class="kv-key">"name"</span><span class="kv-arrow">-&gt;</span><span class="kv-val">"Anu"</span></div>
    <div class="kv-row"><span class="kv-key">"age"</span><span class="kv-arrow">-&gt;</span><span class="kv-val">19</span></div>
    <div class="kv-row"><span class="kv-key">"cgpa"</span><span class="kv-arrow">-&gt;</span><span class="kv-val">8.5</span></div>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><strong>Keys</strong> must be unique and immutable. <strong>Values</strong> can be anything — even another dict.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
