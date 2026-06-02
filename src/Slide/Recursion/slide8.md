---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 8 — ADVANTAGES OF RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Advantages of Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">Advantages</span> of Recursion</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
    <div class="icon-circle ic-green">C</div>
    <div>
      <div class="slide-h3">Clean &amp; Elegant Code</div>
      <div class="small-text">Complex problems become short, readable, and mathematically clean.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
    <div class="icon-circle ic-blue">S</div>
    <div>
      <div class="slide-h3">Solves Naturally Recursive Problems</div>
      <div class="small-text">Trees, graphs, and divide-and-conquer algorithms are naturally recursive.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--purple);">
    <div class="icon-circle ic-purple">D</div>
    <div>
      <div class="slide-h3">Divide and Conquer</div>
      <div class="small-text">Break a big problem into identical smaller sub-problems effortlessly.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">R</div>
    <div>
      <div class="slide-h3">Reduces Code Length</div>
      <div class="small-text">Tower of Hanoi needs 4 lines recursively — dozens iteratively.</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Recursion vs Loop — Code Length</div>

  <div v-after class="g2" style="gap:8px;">
    <div class="flex-col">
      <div class="section-label" style="color:var(--red);">Factorial — Loop</div>
      <div class="code-block" style="font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fact_loop</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#0e6ead;">result</span> = <span style="color:#b45309;">1</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#0e6ead;">n</span>+<span style="color:#b45309;">1</span>):</span>
        <span style="padding-left:32px;display:block;"><span style="color:#0e6ead;">result</span> *= <span style="color:#0e6ead;">i</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">result</span></span>
      </div>
    </div>
    <div class="flex-col">
      <div class="section-label" style="color:var(--green);">Factorial — Recursion</div>
      <div class="code-block" style="font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fact_rec</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
        <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">fact_rec</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;font-size:.7rem;">
    <div>Recursion perfectly mirrors the <strong>mathematical definition</strong>: n! = n * (n-1)!</div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Best-Use Cases for Recursion</div>
  <div v-after style="display:flex;flex-wrap:wrap;gap:6px;margin-top:4px;">
    <span class="pill pill-blue">Tree traversal</span>
    <span class="pill pill-green">Sorting algorithms</span>
    <span class="pill pill-purple">Fibonacci</span>
    <span class="pill pill-orange">Tower of Hanoi</span>
    <span class="pill pill-red">Binary search</span>
    <span class="pill pill-navy">Maze solving</span>
  </div>
</div>

</div>

  </template>
</Slide2>
