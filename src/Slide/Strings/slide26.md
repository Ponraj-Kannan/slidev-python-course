

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">String <span class="highlight">Best Practices</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-green" style="border-radius:10px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--green);margin-bottom:4px;">Use f-strings over % and format()</div>
    <div style="background:#f0fff4;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#6b7280;"># Prefer this</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Hello, <span style="color:#ef5050;">{name}</span>! You are <span style="color:#ef5050;">{age}</span>."</span>)<br>
      <span style="color:#6b7280;"># Not this</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Hello, %s! You are %d."</span> % (<span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>))
    </div>
  </div>

  <div v-click class="card-green" style="border-radius:10px;margin-top:8px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--green);margin-bottom:4px;">Use join() for building large strings</div>
    <div style="background:#f0fff4;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#6b7280;"># Slow — creates many intermediate strings</span><br>
      <span style="color:#0e6ead;">result</span> = <span style="color:#2d7a00;">""</span><br>
      <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">w</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">words</span>: <span style="color:#0e6ead;">result</span> += <span style="color:#0e6ead;">w</span><br><br>
      <span style="color:#6b7280;"># Fast and Pythonic</span><br>
      <span style="color:#0e6ead;">result</span> = <span style="color:#2d7a00;">" "</span>.join(<span style="color:#0e6ead;">words</span>)
    </div>
  </div>

  <div v-click class="card-green" style="border-radius:10px;margin-top:8px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--green);margin-bottom:4px;">Normalise user input immediately</div>
    <div style="background:#f0fff4;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">user</span> = <span style="color:#ef5050;">input</span>(<span style="color:#2d7a00;">"Name: "</span>).strip().title()<br>
      <span style="color:#0e6ead;">city</span> = <span style="color:#ef5050;">input</span>(<span style="color:#2d7a00;">"City: "</span>).strip().lower()
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="card-green" style="border-radius:10px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--green);margin-bottom:4px;">Use raw strings for paths and regex</div>
    <div style="background:#f0fff4;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">path</span>    = <span style="color:#2d7a00;">r"C:\Users\Alice\data.csv"</span><br>
      <span style="color:#0e6ead;">pattern</span> = <span style="color:#2d7a00;">r"\d{3}-\d{4}"</span>  <span style="color:#6b7280;"># phone regex</span>
    </div>
  </div>

  <div v-click class="card-green" style="border-radius:10px;margin-top:8px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--green);margin-bottom:4px;">Use in for substring checks (not find())</div>
    <div style="background:#f0fff4;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#6b7280;"># Cleaner and more readable</span><br>
      <span style="color:#ef5050;">if</span> <span style="color:#2d7a00;">"@"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">email</span>: ...<br><br>
      <span style="color:#6b7280;"># Avoid this pattern for simple checks</span><br>
      <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">email</span>.find(<span style="color:#2d7a00;">"@"</span>) != <span style="color:#b45309;">-1</span>: ...
    </div>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Quick Reference Summary</div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;">
      <span class="pill pill-green">f-strings</span>
      <span class="pill pill-green">join()</span>
      <span class="pill pill-green">strip().lower()</span>
      <span class="pill pill-green">in for search</span>
      <span class="pill pill-green">raw strings</span>
      <span class="pill pill-green">str() to convert</span>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:8px; margin-bottom:40px">
    <div>Writing clean string code isn't just style — it makes programs <strong>faster, safer, and easier to debug</strong> in real projects.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
