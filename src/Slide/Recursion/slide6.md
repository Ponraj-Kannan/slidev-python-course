---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 6 — FUNCTION CALL STACK
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Function Call Stack in Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Function <span class="highlight">Call Stack</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.7;color:var(--slate);">
      The <strong style="color:var(--red);">call stack</strong> is a memory structure that tracks all active function calls. Each call gets a <strong style="color:var(--blue);">stack frame</strong> storing its local variables and return address.
    </div>
  </div>

  <div v-click class="code-block" style="margin-top:4px;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>: <span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#0e6ead;">factorial</span>(<span style="color:#b45309;">3</span>)
  </div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div><strong>Stack overflow risk!</strong> Deep recursion fills up the stack. Python's default limit is around <strong>1000</strong> frames. Use <span class="mono">sys.setrecursionlimit()</span> carefully.</div>
  </div>

  <div v-click class="card-orange" style="font-size:.75rem; margin-bottom:40px;">
    <strong>Each stack frame stores:</strong>
    <div style="display:flex;gap:6px;flex-wrap:wrap;margin-top:6px;">
      <span class="pill pill-orange">local variables</span>
      <span class="pill pill-blue">parameter values</span>
      <span class="pill pill-purple">return address</span>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Stack Growth — factorial(3)</div>

  <div style="background:#f7f8fc;border:1px solid var(--border);border-radius:10px;padding:12px 16px;">
    <div v-after class="small-text" style="text-align:center;margin-bottom:8px;font-weight:700;">CALL STACK (grows downward)</div>
    <div v-click class="stack-frame top">factorial(3) &nbsp; n=3 &nbsp; waiting...</div>
    <div v-click class="stack-frame middle">factorial(2) &nbsp; n=2 &nbsp; waiting...</div>
    <div v-click class="stack-frame" style="border-color:var(--blue);background:#ebf8ff;color:#2b6cb0;">factorial(1) &nbsp; n=1 &nbsp; returns 1</div>
    <div class="small-text" style="text-align:center;margin-top:8px;" v-click>&#x25B2; Stack unwinds from here</div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Stack Unwinding</div>

  <div style="background:#f7f8fc;border:1px solid var(--border);border-radius:10px;padding:12px 16px;">
    <div class="stack-frame done" v-click>factorial(1) = 1 &nbsp; popped</div>
    <div class="stack-frame done" v-click>factorial(2) = 2*1 = 2 &nbsp; popped</div>
    <div class="stack-frame done" v-click>factorial(3) = 3*2 = 6 &nbsp; popped</div>
    <div class="small-text" style="text-align:center;margin-top:8px;color:var(--green);font-weight:700;" v-click>Final result: 6</div>
  </div>
</div>

</div>

  </template>
</Slide2>
