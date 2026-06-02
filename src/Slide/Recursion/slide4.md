---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 4 — HOW RECURSION WORKS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="How Recursion Works — Execution Model">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">How <span class="highlight">Recursion Works</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Two Phases of Recursion</div>

  <div v-after class="g2" style="gap:8px;">
    <div class="card-blue" style="text-align:center;">
      <div class="slide-h3" style="color:var(--blue);">Winding Phase</div>
      <div class="small-text" style="margin-top:4px;">Function keeps calling itself — frames pile up on the stack.</div>
    </div>
    <div class="card-purple" style="text-align:center;">
      <div class="slide-h3" style="color:var(--purple);">Unwinding Phase</div>
      <div class="small-text" style="margin-top:4px;">Base case hit — frames return values and pop off one by one.</div>
    </div>
  </div>

  <div v-click class="code-block" style="margin-top:6px;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>: <span style="color:#6b7280;"># base case</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">factorial</span>(<span style="color:#b45309;">4</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">24</div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div><strong>Think of recursion in two directions:</strong> DOWN (calling) and UP (returning). Results travel back up the chain.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Step-by-Step — factorial(4)</div>

  <div style="display:flex;flex-direction:column;gap:3px;padding:6px 0;">
    <div v-click style="display:flex;align-items:center;gap:6px;">
      <div class="flow-node flow-call" style="flex:1;">factorial(4)</div>
      <div class="small-text">&#x2192; 4 * factorial(3)</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:14px;">
      <div class="flow-node flow-call" style="flex:1;">factorial(3)</div>
      <div class="small-text">&#x2192; 3 * factorial(2)</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:28px;">
      <div class="flow-node flow-call" style="flex:1;">factorial(2)</div>
      <div class="small-text">&#x2192; 2 * factorial(1)</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:42px;">
      <div class="flow-node flow-end" style="flex:1;">factorial(1) = 1</div>
      <div class="small-text">Base case!</div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Unwinding — returning values</div>

  <div style="display:flex;flex-direction:column;gap:3px;padding:4px 0;">
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:28px;">
      <div class="flow-node flow-return" style="flex:1;">factorial(2) = 2 * 1 = 2</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;padding-left:14px;">
      <div class="flow-node flow-return" style="flex:1;">factorial(3) = 3 * 2 = 6</div>
    </div>
    <div v-click style="display:flex;align-items:center;gap:6px;">
      <div class="flow-node flow-body" style="flex:1;">factorial(4) = 4 * 6 = <strong>24</strong></div>
    </div>
  </div>

  <div v-click class="card card-green" style="margin-top:4px;">
    <div class="small-text"><strong>Pattern:</strong> <span class="pill pill-blue">Down</span> divides the problem. <span class="pill pill-purple">Up</span> combines the answers.</div>
  </div>
</div>

</div>

  </template>
</Slide2>
