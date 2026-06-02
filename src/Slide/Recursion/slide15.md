---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — DEBUGGING RECURSIVE FUNCTIONS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Debugging Recursive Functions">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Debugging</span> Recursive Functions</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Common Mistakes</div>

  <div v-after class="flex-col" style="gap:6px;">
    <div class="card" style="border:1px solid var(--red);font-size:.75rem;">
      <strong style="color:var(--red);">Mistake 1 — Missing base case</strong>
      <div class="code-block" style="margin-top:6px;font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">n</span> + <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>) <span style="color:#6b7280;"># never stops</span></span>
      </div>
    </div>
    <div class="card" style="border:1px solid var(--orange);font-size:.75rem;">
      <strong style="color:var(--orange);">Mistake 2 — Wrong base condition</strong>
      <div class="code-block" style="margin-top:6px;font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">-1</span>: <span style="color:#6b7280;"># skips n=0!</span></span>
        <span style="padding-left:32px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
      </div>
    </div>
    <div class="card" style="border:1px solid var(--purple);font-size:.75rem;  margin-bottom:40px;">
      <strong style="color:var(--purple);">Mistake 3 — Not reducing input</strong>
      <div class="code-block" style="margin-top:6px;font-size:.68rem;">
        <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">0</span>: <span style="color:#ef5050;">return</span> <span style="color:#b45309;">0</span></span>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">bad</span>(<span style="color:#0e6ead;">n</span>) <span style="color:#6b7280;"># n not shrinking!</span></span>
      </div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Debugging Technique — Add print()</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#6b7280;"># Debug: trace calls</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Called: factorial({<span style="color:#0e6ead;">n</span>})"</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">n</span> == <span style="color:#b45309;">1</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">result</span> = <span style="color:#0e6ead;">n</span> * <span style="color:#0e6ead;">factorial</span>(<span style="color:#0e6ead;">n</span>-<span style="color:#b45309;">1</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Returning: {<span style="color:#0e6ead;">result</span>} for n={<span style="color:#0e6ead;">n</span>}"</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">result</span></span>
  </div>

  <div v-click class="output-box" style="font-size:.68rem;line-height:1.8;">
    Called: factorial(3)<br>
    Called: factorial(2)<br>
    Called: factorial(1)<br>
    Returning: 1 for n=1<br>
    Returning: 2 for n=2<br>
    Returning: 6 for n=3
  </div>

  <div v-click class="callout callout-success" style="font-size:.7rem;">
    <div><strong>Debug Tips:</strong> <span class="pill pill-green">print at entry</span> <span class="pill pill-blue">print at return</span> <span class="pill pill-orange">use indent levels</span></div>
  </div>
</div>

</div>

  </template>
</Slide2>
