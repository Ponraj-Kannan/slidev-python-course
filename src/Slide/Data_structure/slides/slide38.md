<Slide2 topic="Dictionaries — Practical Examples">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Dictionaries — <span class="highlight">Practical</span> Examples</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Example 1 — Marks Sheet</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">marks</span> = {<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"math"</span>: <span style="color:#b45309;">90</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"science"</span>: <span style="color:#b45309;">82</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"english"</span>: <span style="color:#b45309;">76</span></span>
    }<br>
    <span style="color:#0e6ead;">total</span> = <span style="color:#2d7a00;">sum</span>(<span style="color:#0e6ead;">marks</span>.<span style="color:#0e6ead;">values</span>())<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Total ="</span>, <span style="color:#0e6ead;">total</span>)
  </div>

  <div v-click class="output-box">Total = 248</div>

  <div v-click class="section-label" style="margin-top:6px;">Example 2 — Character Count</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">word</span> = <span style="color:#2d7a00;">"banana"</span><br>
    <span style="color:#0e6ead;">freq</span> = {}<br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">c</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">word</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">freq</span>[<span style="color:#0e6ead;">c</span>] = <span style="color:#0e6ead;">freq</span>.<span style="color:#0e6ead;">get</span>(<span style="color:#0e6ead;">c</span>, <span style="color:#b45309;">0</span>) + <span style="color:#b45309;">1</span></span>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">freq</span>)
  </div>

  <div v-click class="output-box">{'b': 1, 'a': 3, 'n': 2}</div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 3 — Contact Book</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">phone</span> = {<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"Anu"</span>: <span style="color:#2d7a00;">"9876543210"</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"Ravi"</span>: <span style="color:#2d7a00;">"9123456780"</span></span>
    }<br>
    <br>
    <span style="color:#6b7280;"># Add new</span><br>
    <span style="color:#0e6ead;">phone</span>[<span style="color:#2d7a00;">"Sita"</span>] = <span style="color:#2d7a00;">"9009009000"</span><br>
    <br>
    <span style="color:#6b7280;"># Lookup</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">phone</span>[<span style="color:#2d7a00;">"Ravi"</span>])
  </div>

  <div v-click class="output-box">9123456780</div>

  <div v-click class="section-label" style="margin-top:6px;">Example 4 — Max Value Key</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">scores</span> = {<span style="color:#2d7a00;">"A"</span>: <span style="color:#b45309;">72</span>, <span style="color:#2d7a00;">"B"</span>: <span style="color:#b45309;">91</span>, <span style="color:#2d7a00;">"C"</span>: <span style="color:#b45309;">88</span>}<br>
    <span style="color:#0e6ead;">top</span> = <span style="color:#2d7a00;">max</span>(<span style="color:#0e6ead;">scores</span>, <span style="color:#0e6ead;">key</span>=<span style="color:#0e6ead;">scores</span>.<span style="color:#0e6ead;">get</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">top</span>)
  </div>

  <div v-click class="output-box">B</div>
</div>

</div>

  </template>
</Slide2>
