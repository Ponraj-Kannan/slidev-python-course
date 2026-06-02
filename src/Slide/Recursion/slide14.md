---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — RECURSIVE PROBLEM SOLVING
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Recursive Problem Solving Strategy">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Recursive <span class="highlight">Problem Solving</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">3-Step Strategy</div>

  <div v-after style="display:flex;flex-direction:column;gap:6px;">
    <div class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--red);">
      <div class="icon-circle ic-red" style="font-size:.9rem;">1</div>
      <div>
        <div class="slide-h3">Identify the Base Case</div>
        <div class="small-text">When is the answer trivially known? (n==0, empty list, single char)</div>
      </div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--blue);">
      <div class="icon-circle ic-blue" style="font-size:.9rem;">2</div>
      <div>
        <div class="slide-h3">Define the Recursive Case</div>
        <div class="small-text">How does the current problem relate to a smaller version of itself?</div>
      </div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;border:1px solid var(--green);">
      <div class="icon-circle ic-green" style="font-size:.9rem;">3</div>
      <div>
        <div class="slide-h3">Trust the Recursion</div>
        <div class="small-text">Assume the recursive call works correctly and build your solution around it.</div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="font-size:.7rem;">
    <div><strong>Tip:</strong> Write the base case first, then the recursive case. Never start coding from the recursive case.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Apply the Strategy — Fibonacci</div>

  <div v-after class="card-navy" style="border-radius:10px;font-size:.75rem;line-height:1.7;">
    <strong>Step 1 — Base:</strong> fib(0) = 0, fib(1) = 1<br>
    <strong>Step 2 — Recursive:</strong> fib(n) = fib(n-1) + fib(n-2)<br>
    <strong>Step 3 — Trust:</strong> Call fib(n-1) and fib(n-2) and add them.
  </div>

  <div v-click class="code-block" style="margin-top:6px;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> &lt;= <span style="color:#b45309;">1</span>: <span style="color:#6b7280;"># base case</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>) + <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">2</span>)</span>
    <br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">7</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">i</span>), <span style="color:#0e6ead;">end</span>=<span style="color:#2d7a00;">" "</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">0  1  1  2  3  5  8</div>

  <div v-click class="section-label" style="margin-top:6px;">Fibonacci Recursion Tree</div>
  <div v-after style="text-align:center;font-family:'Fira Code',monospace;font-size:.64rem;line-height:2; margin-bottom:40px; background:#f7f8fc;border:1px solid var(--border);border-radius:8px;padding:6px;">
    <div><span style="color:#2b6cb0;font-weight:700;">fib(4)</span></div>
    <div><span style="color:#2b6cb0;">fib(3)</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; + &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:#2b6cb0;">fib(2)</span></div>
    <div><span style="color:#dd6b20;">fib(2)</span> + <span style="color:#dd6b20;">fib(1)</span> &nbsp;&nbsp; <span style="color:#dd6b20;">fib(1)</span> + <span style="color:#dd6b20;">fib(0)</span></div>
    <div><span style="color:#276749;font-weight:700;">1+1</span> &nbsp;&nbsp;&nbsp; <span style="color:#276749;font-weight:700;">1</span> &nbsp;&nbsp;&nbsp; <span style="color:#276749;font-weight:700;">1</span> &nbsp;&nbsp;&nbsp; <span style="color:#276749;font-weight:700;">0</span></div>
  </div>
</div>

</div>

  </template>
</Slide2>
