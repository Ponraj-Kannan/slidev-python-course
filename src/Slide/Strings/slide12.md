<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">String Methods — <span class="highlight">Split &amp; Join</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">split()</strong> breaks a string into a <strong>list of substrings</strong>. <strong style="color:var(--red);">join()</strong> does the opposite — it combines a list of strings into <strong>one string</strong> with a separator.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">split() — String → List</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">sentence</span> = <span style="color:#2d7a00;">"Python is fun"</span><br>
    <span style="color:#0e6ead;">words</span> = <span style="color:#0e6ead;">sentence</span>.split()  <span style="color:#6b7280;"># splits on whitespace</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">words</span>)  <span style="color:#6b7280;"># ['Python', 'is', 'fun']</span><br><br>
    <span style="color:#6b7280;"># Custom separator</span><br>
    <span style="color:#0e6ead;">csv</span> = <span style="color:#2d7a00;">"Alice,25,Engineer"</span><br>
    <span style="color:#0e6ead;">fields</span> = <span style="color:#0e6ead;">csv</span>.split(<span style="color:#2d7a00;">","</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fields</span>)  <span style="color:#6b7280;"># ['Alice', '25', 'Engineer']</span><br><br>
    <span style="color:#6b7280;"># Limit number of splits</span><br>
    <span style="color:#0e6ead;">text</span> = <span style="color:#2d7a00;">"a:b:c:d"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">text</span>.split(<span style="color:#2d7a00;">":"</span>, <span style="color:#b45309;">2</span>))  <span style="color:#6b7280;"># ['a', 'b', 'c:d']</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">join() — List → String</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">words</span> = [<span style="color:#2d7a00;">"Python"</span>, <span style="color:#2d7a00;">"is"</span>, <span style="color:#2d7a00;">"fun"</span>]<br>
    <span style="color:#0e6ead;">result</span> = <span style="color:#2d7a00;">" "</span>.join(<span style="color:#0e6ead;">words</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span>)  <span style="color:#6b7280;"># Python is fun</span><br><br>
    <span style="color:#6b7280;"># Join with comma</span><br>
    <span style="color:#0e6ead;">items</span> = [<span style="color:#2d7a00;">"apple"</span>, <span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"cherry"</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">", "</span>.join(<span style="color:#0e6ead;">items</span>))<br>
    <span style="color:#6b7280;"># apple, banana, cherry</span><br><br>
    <span style="color:#6b7280;"># Join with no separator</span><br>
    <span style="color:#0e6ead;">chars</span> = [<span style="color:#2d7a00;">"H"</span>, <span style="color:#2d7a00;">"i"</span>, <span style="color:#2d7a00;">"!"</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">""</span>.join(<span style="color:#0e6ead;">chars</span>))  <span style="color:#6b7280;"># Hi!</span>
  </div>

  <div v-click class="step-flow" style="margin-top:10px;justify-content:center;">
    <div class="step-box active">String</div>
    <div class="step-arrow">→</div>
    <div class="step-box">split(",")</div>
    <div class="step-arrow">→</div>
    <div class="step-box">List</div>
    <div class="step-arrow">→</div>
    <div class="step-box">join(", ")</div>
    <div class="step-arrow">→</div>
    <div class="step-box active">String</div>
  </div>

  <div v-click class="card card-orange" style="margin-top:8px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> Parsing CSV files, building comma-separated lists, splitting sentences into words for analysis</div>
  </div>

</div>

</div>

  </template>
</Slide2>
