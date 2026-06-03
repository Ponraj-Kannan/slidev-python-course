<Slide2 topic="Creating Tuples">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Creating</span> Tuples</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Four Common Ways</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Empty tuple</span><br>
    <span style="color:#0e6ead;">a</span> = ()<br>
    <br>
    <span style="color:#6b7280;"># Single element — needs trailing comma!</span><br>
    <span style="color:#0e6ead;">b</span> = (<span style="color:#b45309;">5</span>,)<br>
    <br>
    <span style="color:#6b7280;"># Multiple values</span><br>
    <span style="color:#0e6ead;">c</span> = (<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>)<br>
    <br>
    <span style="color:#6b7280;"># Without parentheses (still a tuple)</span><br>
    <span style="color:#0e6ead;">d</span> = <span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span><br>
    <br>
    <span style="color:#6b7280;"># From other iterables</span><br>
    <span style="color:#0e6ead;">e</span> = <span style="color:#2d7a00;">tuple</span>([<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>])
  </div>
</div>

<div class="flex-col">

  <div v-click class="section-label" style="margin-top:6px;">Verify the Difference</div>

  <div v-after class="code-block">
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">type</span>((<span style="color:#b45309;">5</span>)))   <span style="color:#6b7280;"># int</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">type</span>((<span style="color:#b45309;">5</span>,)))  <span style="color:#6b7280;"># tuple</span>
  </div>

  <div v-click class="output-box">
    &lt;class 'int'&gt;<br>
    &lt;class 'tuple'&gt;
  </div>

  <div v-click class="card card-blue" style="margin-top:4px;">
    <div class="small-text"><strong>Tip:</strong> <span class="mono">tuple()</span> with no argument also creates an empty tuple.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
