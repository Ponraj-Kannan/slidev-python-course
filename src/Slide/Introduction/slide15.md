---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 4 — VARIABLE DECLARATION & ASSIGNMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Variable <span class="highlight">Declaration</span> &amp; <span class="highlight">Assignment</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="section-label">Syntax Structure</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px;font-family:'Fira Code',monospace;font-size:.85rem;line-height:2.2;">
    <span style="color:#0e6ead;">variable_name</span> <span style="color:#c49a00;">=</span> <span style="color:#2d7a00;">value</span>
  </div>

  <div v-click style="margin-top:6px;display:flex;flex-direction:column;gap:6px;border:1px solid #e1e4e8;padding:10px;border-radius:10px;">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-varname">variable_name</span>
      <span class="body-text">The label/identifier for the stored value</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-operator">=</span>
      <span class="body-text">Assignment operator (not equality!)</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-value">value</span>
      <span class="body-text">The data to store (number, text, etc.)</span>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:4px;">
    <div><strong>Note:</strong> In Python, <span class="mono">=</span> means <em>assignment</em>. It means "store this value". It does NOT mean "is equal to" like in math.</div>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Assignment Flow</div>
  <div v-after style="display:flex;align-items:center;gap:6px;flex-wrap:wrap;">
    <div class="step-box active">Write Name</div>
    <div class="step-arrow">→</div>
    <div class="step-box active">= operator</div>
    <div class="step-arrow">→</div>
    <div class="step-box active">Provide Value</div>
    <div class="step-arrow">→</div>
    <div class="step-box" style="border-color:var(--green);background:#f0fff4;color:var(--green);">Stored!</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Examples</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># Integer</span><br>
    <span style="color:#0e6ead;">age</span> <span style="color:#c49a00;">=</span> <span style="color:#b45309;">25</span><br>
    <span style="color:#6b7280;"># Float</span><br>
    <span style="color:#0e6ead;">price</span> <span style="color:#c49a00;">=</span> <span style="color:#b45309;">99.99</span><br>
    <span style="color:#6b7280;"># String</span><br>
    <span style="color:#0e6ead;">city</span> <span style="color:#c49a00;">=</span> <span style="color:#2d7a00;">"Chennai"</span><br>
    <span style="color:#6b7280;"># Boolean</span><br>
    <span style="color:#0e6ead;">is_student</span> <span style="color:#c49a00;">=</span> <span style="color:#ef5050;">True</span>
  </div>

  <div v-click class="mem-box" style="margin-top:6px;">
    <div class="mem-header">Memory After Assignment</div>
    <div class="mem-row">
      <div class="mem-name">age</div>
      <div class="mem-val">25</div>
      <div class="mem-type">int</div>
    </div>
    <div class="mem-row">
      <div class="mem-name">price</div>
      <div class="mem-val">99.99</div>
      <div class="mem-type">float</div>
    </div>
    <div class="mem-row">
      <div class="mem-name">city</div>
      <div class="mem-val">"Chennai"</div>
      <div class="mem-type">str</div>
    </div>
    <div class="mem-row">
      <div class="mem-name">is_student</div>
      <div class="mem-val">True</div>
      <div class="mem-type">bool</div>
    </div>
  </div>

</div>

</div>

  </template>
</Slide2>
