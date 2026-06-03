<Slide2 topic="Common Mistakes — Lists &amp; Tuples">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Common Mistakes — <span class="highlight">Lists</span> &amp; <span class="highlight">Tuples</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-red">
    <div class="slide-h3" style="color:var(--red-dark);">List: Index Out of Range</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>[<span style="color:#b45309;">5</span>])<br>
      <span style="color:#c0392b;font-weight:700;"># IndexError</span>
    </div>
    <div class="small-text" style="margin-top:4px;"><strong>Fix:</strong> Check <span class="mono">len()</span> first or use <span class="mono">try/except</span>.</div>
  </div>

  <div v-click class="card card-red">
    <div class="slide-h3" style="color:var(--red-dark);">List: Wrong Slicing</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">n</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>]<br>
      <span style="color:#6b7280;"># Hoping to get [2,3,4]</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>[<span style="color:#b45309;">1</span>:<span style="color:#b45309;">3</span>])  <span style="color:#6b7280;"># [2, 3]</span>
    </div>
    <div class="small-text" style="margin-top:4px;"><strong>Remember:</strong> <span class="mono">stop</span> is exclusive.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-orange">
    <div class="slide-h3" style="color:var(--orange);">Tuple: Trying to Modify</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">t</span> = (<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>)<br>
      <span style="color:#0e6ead;">t</span>[<span style="color:#b45309;">0</span>] = <span style="color:#b45309;">99</span><br>
      <span style="color:#c0392b;font-weight:700;"># TypeError</span>
    </div>
    <div class="small-text" style="margin-top:4px;"><strong>Fix:</strong> Use a list, or recreate the tuple from a list.</div>
  </div>

  <div v-click class="card card-orange">
    <div class="slide-h3" style="color:var(--orange);">Tuple: Forgot the Comma</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">t</span> = (<span style="color:#b45309;">5</span>)   <span style="color:#6b7280;"># this is int!</span><br>
      <span style="color:#0e6ead;">t</span> = (<span style="color:#b45309;">5</span>,)  <span style="color:#6b7280;"># this is tuple</span>
    </div>
    <div class="small-text" style="margin-top:4px;"><strong>Fix:</strong> Always add a comma for single-element tuples.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
