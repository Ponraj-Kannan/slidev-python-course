---
theme: default
title: Python Looping Statements
titleTemplate: '%s — Python Fundamentals'
highlighter: shiki
lineNumbers: true
drawings:
  persist: false
transition: slide-left
mdc: true
colorSchema: light
fonts:
  sans: 'Nunito'
  mono: 'Fira Code'
---

<Slide2 topic="Introduction to Loops">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;">What is a <span class="highlight">Loop ?</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">loop</strong> is a programming construct that <strong style="color:var(--green);">repeats a block of code</strong> multiple times — until a condition becomes false or the sequence is exhausted.
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Without a loop:</strong> Printing 1 to 100 requires 100 print() statements. With a loop — just 3 lines!</div>
  </div>

  <div v-click class="card card-red" style="margin-top:4px;">
    <div class="slide-h3" style="margin-bottom:6px;">Real-World Analogy</div>
    <div class="body-text">A washing machine runs the wash cycle <strong>repeatedly</strong> until the timer ends. That is exactly what a loop does in code.</div>
  </div>

  <div v-click class="card card-green">
    <div class="small-text"><strong>Key benefit:</strong> Write code <strong>once</strong>, execute it <strong>n</strong> times — reduces repetition and errors.</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="slide-h3" style="margin-bottom:8px;">Without Loop vs With Loop</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.8;">
    <div style="color:#6b7280;margin-bottom:4px;"># Without loop — repetitive!</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">1</span>)</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">2</span>)</div>
    <div><span style="color:#2d7a00;">print</span>(<span style="color:#b45309;">3</span>)</div>
    <div style="color:#6b7280;">... 97 more lines ...</div>
    <br>
    <div style="color:#6b7280;"># With loop — clean and smart!</div>
    <div><span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">101</span>):</div>
    <div style="padding-left:20px;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>Types of Loops in Python:</strong></div>
    <div style="display:flex;gap:8px;margin-top:6px;flex-wrap:wrap;">
      <span class="pill pill-red">while loop</span>
      <span class="pill pill-blue">for loop</span>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
