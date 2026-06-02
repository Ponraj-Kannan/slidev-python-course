---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 20 — INTRODUCTION TO OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Introduction to <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      An <strong style="color:var(--red);">operator</strong> is a <strong style="color:var(--green);">symbol</strong> that tells Python to perform a specific <strong>mathematical, logical, or relational operation</strong> on values (called <em>operands</em>).
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Think of it like this:</strong> In <span class="mono">5 + 3</span>, the <span class="mono" style="color:var(--red);">+</span> is the operator and <span class="mono">5</span>, <span class="mono">3</span> are operands. The result is <span class="mono" style="color:var(--green);">8</span>.</div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># Operator in action</span><br>
    <span style="color:#0e6ead;">a</span> = <span style="color:#b45309;">10</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#6b7280;"># operand</span><br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#b45309;">3</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#6b7280;"># operand</span><br>
    <span style="color:#0e6ead;">result</span> = <span style="color:#0e6ead;">a</span> <span style="color:#ef5050;">+</span> <span style="color:#0e6ead;">b</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#6b7280;"># + is the operator</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span>) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#6b7280;"># 13</span>
  </div>

</div>

<div class="flex-col">
  <div class="section-label" v-click>Python Operator Categories</div>

  <div style="display:flex;flex-direction:column;gap:5px;">
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-red">Arithmetic</span>
      <span class="small-text" style="align-self:center;">— +  −  *  /  //  %  **</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-blue">Assignment</span>
      <span class="small-text" style="align-self:center;">— =  +=  -=  *=  …</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-orange">Comparison</span>
      <span class="small-text" style="align-self:center;">— ==  !=  >  <  >=  <=</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-green">Logical</span>
      <span class="small-text" style="align-self:center;">— and  or  not</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill pill-navy">Bitwise</span>
      <span class="small-text" style="align-self:center;">— &  |  ^  ~  <<  >></span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill" style="background:#f0e6ff;color:#6b21a8;">Membership</span>
      <span class="small-text" style="align-self:center;">— in  not in</span>
    </div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;" v-click>
      <span class="pill" style="background:#fef9c3;color:#854d0e;">Identity</span>
      <span class="small-text" style="align-self:center;">— is  is not</span>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Operators are the <strong>building blocks</strong> of all expressions in Python — from simple math to complex decision-making.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
