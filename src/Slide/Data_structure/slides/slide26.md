<Slide2 topic="Creating Sets">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Creating</span> Sets</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Ways to Create a Set</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Literal</span><br>
    <span style="color:#0e6ead;">a</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>}<br>
    <br>
    <span style="color:#6b7280;"># From list (removes duplicates)</span><br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#2d7a00;">set</span>([<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>])<br>
    <br>
    <span style="color:#6b7280;"># From string (each char)</span><br>
    <span style="color:#0e6ead;">c</span> = <span style="color:#2d7a00;">set</span>(<span style="color:#2d7a00;">"hello"</span>)<br>
    <br>
    <span style="color:#6b7280;"># Empty set — MUST use set()</span><br>
    <span style="color:#0e6ead;">d</span> = <span style="color:#2d7a00;">set</span>()
  </div>
</div>

<div class="flex-col">
  <div v-click class="callout callout-danger" style="font-size:.7rem;">
    <div><strong>Trap:</strong> <span class="mono">{}</span> creates an empty <strong>dict</strong>, NOT a set! Use <span class="mono">set()</span>.</div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Verify the Difference</div>

  <div v-after class="code-block">
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">type</span>({}))     <span style="color:#6b7280;"># dict</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">type</span>(<span style="color:#2d7a00;">set</span>()))   <span style="color:#6b7280;"># set</span>
  </div>

  <div v-click class="output-box">
    &lt;class 'dict'&gt;<br>
    &lt;class 'set'&gt;
  </div>

  <div v-click class="card card-blue" style="margin-top:4px;">
    <div class="small-text"><strong>Tip:</strong> Casting a list to a set is the quickest way to remove duplicates.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
