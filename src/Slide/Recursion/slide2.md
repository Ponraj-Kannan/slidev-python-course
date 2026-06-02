<!-- ═══════════════════════════════════════════════════════
     SLIDE 2 — INTRODUCTION TO RECURSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Introduction to Recursion">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What is <span class="highlight">Recursion ?</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Recursion</strong> is a technique where a function <strong style="color:var(--green);">calls itself</strong> to solve a smaller version of the same problem — until it reaches a <strong style="color:var(--blue);">stopping condition</strong>.
    </div>
  </div>
  <div v-click class="callout callout-success">
    <div><strong>Key idea:</strong> Recursion breaks a big problem into a <strong>smaller version of itself</strong>, solves the smallest case, then builds back up.</div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Syntax Structure</div>

  <div v-click class="code-block" style="font-size:.78rem;line-height:2;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">function_name</span>(<span style="color:#c49a00;">parameters</span>)<span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Base Case — stopping condition</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">base_condition</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">base_value</span></span>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Recursive Case — calls itself</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">function_name</span>(<span style="color:#0e6ead;">smaller_input</span>)</span>
  </div>
</div>
<div class="flex-col">

  <div style="margin-top:4px; border:1px solid #e1e4e808; padding:10px; border-radius:10px;">
    <div v-click class="section-label" style="margin-bottom:6px;">Syntax Parts</div>
    <div style="display:flex;flex-direction:column;gap:5px;">
      <div style="display:flex;gap:8px;align-items:center;"  v-click>
        <span class="syn-keyword">def</span>
        <span class="body-text">Starts the function definition</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;" v-click>
        <span class="syn-varname">base_condition</span>
        <span class="body-text">When to stop calling itself</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;" v-click>
        <span class="syn-operator">return base_value</span>
        <span class="body-text">Return a direct answer at the base</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;" v-click>
        <span class="syn-value">function_name(smaller_input)</span>
        <span class="body-text">The recursive call with reduced input</span>
      </div>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
