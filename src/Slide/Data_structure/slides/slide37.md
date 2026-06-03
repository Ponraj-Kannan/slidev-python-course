<Slide2 topic="Traversing &amp; Nested Dictionaries">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Traversing</span> &amp; <span class="highlight">Nested</span> Dictionaries</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Three Ways to Loop</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">d</span> = {<span style="color:#2d7a00;">"a"</span>: <span style="color:#b45309;">1</span>, <span style="color:#2d7a00;">"b"</span>: <span style="color:#b45309;">2</span>}<br>
    <br>
    <span style="color:#6b7280;"># Keys only</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">k</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">d</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">k</span>)</span>
    <br>
    <span style="color:#6b7280;"># Values only</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">v</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">values</span>():<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">v</span>)</span>
    <br>
    <span style="color:#6b7280;"># Both</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">k</span>, <span style="color:#0e6ead;">v</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">items</span>():<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">k</span>, <span style="color:#2d7a00;">":"</span>, <span style="color:#0e6ead;">v</span>)</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Nested Dictionary</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">students</span> = {<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"s1"</span>: {<span style="color:#2d7a00;">"name"</span>: <span style="color:#2d7a00;">"Anu"</span>, <span style="color:#2d7a00;">"cgpa"</span>: <span style="color:#b45309;">8.5</span>},</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"s2"</span>: {<span style="color:#2d7a00;">"name"</span>: <span style="color:#2d7a00;">"Ravi"</span>, <span style="color:#2d7a00;">"cgpa"</span>: <span style="color:#b45309;">7.9</span>}</span>
    }<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">students</span>[<span style="color:#2d7a00;">"s1"</span>][<span style="color:#2d7a00;">"name"</span>])
  </div>

  <div v-click class="output-box">Anu</div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:4px;">Nested Visual</div>
    <div style="background:#f7f8fc;border:1px solid var(--border);padding:8px;border-radius:8px;">
      <div class="kv-row"><span class="kv-key">"s1"</span><span class="kv-arrow">-&gt;</span><span class="kv-val">{name, cgpa}</span></div>
      <div style="margin-top:4px;" class="kv-row"><span class="kv-key">"s2"</span><span class="kv-arrow">-&gt;</span><span class="kv-val">{name, cgpa}</span></div>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
