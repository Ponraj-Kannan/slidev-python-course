<Slide2 topic="Python Collections — Welcome">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">Python <span class="highlight">Collections</span> — Lists, Tuples, Sets &amp; Dictionaries</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">collection</strong> is a single Python object that <strong style="color:var(--green);">stores many values together</strong> — so you can manage groups of data without dozens of separate variables.
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Without a collection:</strong> Storing 100 student marks needs 100 variables. With a list — just one!</div>
  </div>

  <div v-click class="card card-red" style="margin-top:4px;">
    <div class="slide-h3" style="margin-bottom:6px;">Real-World Analogy</div>
    <div class="body-text">A <strong>contact book</strong> stores many phone numbers in one place. A Python collection stores many values inside one container.</div>
  </div>

  <div v-click class="card card-green">
    <div class="small-text"><strong>You'll learn:</strong> four built-in collections — <strong>List</strong>, <strong>Tuple</strong>, <strong>Set</strong>, and <strong>Dictionary</strong>.</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="slide-h3" style="margin-bottom:8px;">One variable — many values</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Without collection — painful!</span><br>
    <span style="color:#0e6ead;">m1</span> = <span style="color:#b45309;">82</span><br>
    <span style="color:#0e6ead;">m2</span> = <span style="color:#b45309;">76</span><br>
    <span style="color:#0e6ead;">m3</span> = <span style="color:#b45309;">91</span><br>
    <span style="color:#6b7280;"># ... up to m100 ...</span><br>
    <br>
    <span style="color:#6b7280;"># With a list — clean!</span><br>
    <span style="color:#0e6ead;">marks</span> = [<span style="color:#b45309;">82</span>, <span style="color:#b45309;">76</span>, <span style="color:#b45309;">91</span>, <span style="color:#b45309;">88</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">sum</span>(<span style="color:#0e6ead;">marks</span>) / <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">marks</span>))
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>Four collection types in Python:</strong></div>
    <div style="display:flex;gap:8px;margin-top:6px;flex-wrap:wrap;">
      <span class="pill pill-red">list</span>
      <span class="pill pill-orange">tuple</span>
      <span class="pill pill-green">set</span>
      <span class="pill pill-blue">dict</span>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
