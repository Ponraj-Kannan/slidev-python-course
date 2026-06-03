<Slide2 topic="Accessing Dictionary Values">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Accessing</span> Dictionary Values</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Square Bracket  d[key]</div>
    <div class="small-text" style="margin-top:4px;">Raises <span class="mono">KeyError</span> if key is missing.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">d</span> = {<span style="color:#2d7a00;">"name"</span>: <span style="color:#2d7a00;">"Anu"</span>, <span style="color:#2d7a00;">"age"</span>: <span style="color:#b45309;">19</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">d</span>[<span style="color:#2d7a00;">"name"</span>])  <span style="color:#6b7280;"># Anu</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">d</span>[<span style="color:#2d7a00;">"city"</span>])  <span style="color:#6b7280;"># KeyError!</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-green" style="text-align:center;">
    <div class="slide-h2" style="color:var(--green);">get()  — safe</div>
    <div class="small-text" style="margin-top:4px;">Returns <span class="mono">None</span> (or a default) when key is missing.</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">get</span>(<span style="color:#2d7a00;">"name"</span>))<br>
    <span style="color:#6b7280;"># Anu</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">get</span>(<span style="color:#2d7a00;">"city"</span>))<br>
    <span style="color:#6b7280;"># None</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">get</span>(<span style="color:#2d7a00;">"city"</span>, <span style="color:#2d7a00;">"NA"</span>))<br>
    <span style="color:#6b7280;"># NA</span>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div>Use <span class="mono">get()</span> when you're not sure if the key exists.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
