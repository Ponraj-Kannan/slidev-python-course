---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 9 — DISADVANTAGES OF RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Disadvantages of Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">Disadvantages</span> of Recursion</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--red);">
    <div class="icon-circle ic-red">M</div>
    <div>
      <div class="slide-h3">High Memory Usage</div>
      <div class="small-text">Each recursive call uses a stack frame. Deep recursion can consume a lot of memory.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--orange);">
    <div class="icon-circle ic-orange">S</div>
    <div>
      <div class="slide-h3">Stack Overflow Risk</div>
      <div class="small-text">Python has a recursion depth limit (~1000). Exceeding it causes <span class="mono" style="font-size:.65rem;">RecursionError</span>.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--yellow);">
    <div class="icon-circle" style="background:#fefcbf;color:#b7791f;">T</div>
    <div>
      <div class="slide-h3">Repeated Calculations</div>
      <div class="small-text">Without memoization, Fibonacci recomputes the same values many times.</div>
    </div>
  </div>

  <div v-click class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--purple);">
    <div class="icon-circle ic-purple">D</div>
    <div>
      <div class="slide-h3">Harder to Debug</div>
      <div class="small-text">Tracing multiple nested calls is trickier than a simple loop.</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common Error — Infinite Recursion</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># WRONG — missing base case!</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">bad_count</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">n</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">bad_count</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># never stops!</span></span>
    <br>
    <span style="color:#0e6ead;">bad_count</span>(<span style="color:#b45309;">5</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;border-color:#f5c6cb;color:#721c24;background:#fff5f5;">
    5, 4, 3, 2, 1, 0, -1, -2 ... <br>
    RecursionError: maximum recursion depth exceeded
  </div>
</div>

</div>

  </template>
</Slide2>
