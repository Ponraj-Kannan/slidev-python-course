---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — PRACTICAL PROGRAMS — FACTORIAL & FIBONACCI
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Programs — Factorial &amp; Fibonacci">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical <span class="highlight">Recursive Programs</span> — Part 1</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Program 1 — Factorial</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># n! = n × (n-1) × ... × 1</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span> <span style="color:#ef5050;">or</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">factorial</span>(<span style="color:#b45309;">5</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">120</div>

  <div v-click class="section-label" style="margin-top:6px;">Execution: factorial(5)</div>
  <div v-after style="display:flex;flex-wrap:wrap;gap:4px;align-items:center;font-size:.65rem;font-family:'Fira Code',monospace;">
    <span class="pill pill-blue">5 × 4!</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">4 × 3!</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">3 × 2!</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">2 × 1!</span>
    <span>&#x2192;</span>
    <span class="pill pill-green">1</span>
    <span>&#x21D0;</span>
    <span class="pill pill-purple">120</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Program 2 — Fibonacci Series</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># fib(n) = fib(n-1) + fib(n-2)</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> &lt;= <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>) + <span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">2</span>)</span>
    <br>
    <span style="color:#6b7280;"># Print first 8 fibonacci numbers</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">8</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fib</span>(<span style="color:#0e6ead;">i</span>), <span style="color:#0e6ead;">end</span>=<span style="color:#2d7a00;">" "</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">0  1  1  2  3  5  8  13</div>

  <div v-click class="section-label" style="margin-top:6px;">Fibonacci — Each Term is Sum of Previous Two</div>
  <div v-after style="display:flex;gap:4px;flex-wrap:wrap;align-items:center;">
    <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">0</div>
    <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">1</div>
    <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">1</div>
    <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">2</div>
    <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);">3</div>
    <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);">5</div>
    <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">8</div>
    <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">13</div>
  </div>
</div>

</div>

  </template>
</Slide2>
