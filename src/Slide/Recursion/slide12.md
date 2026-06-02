---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 12 — INDIRECT RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Indirect Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Indirect</span> Recursion</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.7;color:var(--slate);">
      <strong style="color:var(--red);">Indirect recursion</strong> occurs when <strong style="color:var(--blue);">Function A calls Function B</strong>, and <strong style="color:var(--green);">Function B calls Function A</strong> — forming a cycle.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Indirect Recursion Flow</div>

  <div v-after style="display:flex;justify-content:center;align-items:center;gap:20px;padding:14px;background:#f7f8fc;border:1px solid var(--border);border-radius:10px;">
    <div style="display:flex;flex-direction:column;align-items:center;gap:4px;">
      <div class="flow-node flow-call" style="width:110px;">func_A(n)</div>
      <div class="small-text" style="font-size:.6rem;text-align:center;">calls func_B</div>
    </div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:4px;">
      <div style="color:var(--blue);font-size:1.3rem;font-weight:900;">&#x21C4;</div>
      <div class="small-text" style="font-size:.6rem;">mutual calls</div>
    </div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:4px;">
      <div class="flow-node flow-return" style="width:110px;">func_B(n)</div>
      <div class="small-text" style="font-size:.6rem;text-align:center;">calls func_A</div>
    </div>
  </div>

  <div v-click class="callout callout-warn" style="font-size:.7rem;">
    <div><strong>Important:</strong> Both functions must have proper base cases — otherwise infinite mutual calling occurs.</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example — is_even / is_odd</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># Indirect recursion example</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">is_even</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#ef5050;">True</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">is_odd</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># calls is_odd!</span></span>
    <br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">is_odd</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#ef5050;">False</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">is_even</span>(<span style="color:#0e6ead;">n</span> - <span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># calls is_even!</span></span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">is_even</span>(<span style="color:#b45309;">4</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">is_odd</span>(<span style="color:#b45309;">3</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    True<br>
    True
  </div>

  <div v-click class="section-label" style="margin-top:6px;">How is_even(4) Runs</div>
  <div v-after style="display:flex;flex-wrap:wrap;gap:4px;align-items:center;font-size:.68rem;font-family:'Fira Code',monospace; margin-bottom:40px;">
    <span class="pill pill-blue">is_even(4)</span>
    <span>&#x2192;</span>
    <span class="pill pill-purple">is_odd(3)</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">is_even(2)</span>
    <span>&#x2192;</span>
    <span class="pill pill-purple">is_odd(1)</span>
    <span>&#x2192;</span>
    <span class="pill pill-blue">is_even(0)</span>
    <span>&#x2192;</span>
    <span class="pill pill-green">True</span>
  </div>
</div>

</div>

  </template>
</Slide2>
