---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 17 — PRACTICAL PROGRAMS — POWER & REVERSE STRING
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Practical Programs — Power &amp; Reverse String">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practical Programs — <span class="highlight">Part 2</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Program 3 — Power Calculation</div>

  <div v-after class="code-block">
    <span style="color:#6b7280;"># base^exp using recursion</span><br>
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">exp</span> == <span style="color:#b45309;">0</span>: <span style="color:#6b7280;"># anything^0 = 1</span></span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#b45309;">1</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">base</span> * <span style="color:#0e6ead;">power</span>(<span style="color:#0e6ead;">base</span>, <span style="color:#0e6ead;">exp</span> - <span style="color:#b45309;">1</span>)</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">power</span>(<span style="color:#b45309;">2</span>, <span style="color:#b45309;">5</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">power</span>(<span style="color:#b45309;">3</span>, <span style="color:#b45309;">3</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    32 &nbsp;<span class="comment"># 2^5 = 2*2*2*2*2</span><br>
    27 &nbsp;<span class="comment"># 3^3 = 3*3*3</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">How power(2,4) works</div>
  <div v-after style="font-size:.68rem;font-family:'Fira Code',monospace;line-height:2; margin-bottom:40px;">
    <div><span class="pill pill-blue">power(2,4)</span> = 2 * power(2,3)</div>
    <div style="padding-left:14px;"><span class="pill pill-blue">power(2,3)</span> = 2 * power(2,2)</div>
    <div style="padding-left:28px;"><span class="pill pill-blue">power(2,2)</span> = 2 * power(2,1)</div>
    <div style="padding-left:42px;"><span class="pill pill-blue">power(2,1)</span> = 2 * power(2,0)</div>
    <div style="padding-left:56px;"><span class="pill pill-green">power(2,0)</span> = 1 (base)</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Program 4 — Reverse a String</div>

  <div v-after class="code-block">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">reverse_str</span>(<span style="color:#0e6ead;">s</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#2d7a00;">len</span>(<span style="color:#0e6ead;">s</span>) == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">""</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#0e6ead;">reverse_str</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">1</span>:]) + <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>]</span>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">reverse_str</span>(<span style="color:#2d7a00;">"Python"</span>))<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">reverse_str</span>(<span style="color:#2d7a00;">"Hello"</span>))
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    nohtyP<br>
    olleH
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Logic Visualization — "ABC"</div>
  <div v-after style="display:flex;flex-direction:column;gap:3px;font-size:.68rem;font-family:'Fira Code',monospace;">
    <div><span class="pill pill-blue">reverse("ABC")</span> = reverse("BC") + "A"</div>
    <div style="padding-left:14px;"><span class="pill pill-blue">reverse("BC")</span> = reverse("C") + "B"</div>
    <div style="padding-left:28px;"><span class="pill pill-blue">reverse("C")</span> = reverse("") + "C"</div>
    <div style="padding-left:42px;"><span class="pill pill-green">reverse("")</span> = "" (base)</div>
    <div style="color:var(--purple);font-weight:700;padding-left:14px;">= "" + "C" + "B" + "A" = "CBA"</div>
  </div>
</div>

</div>

  </template>
</Slide2>
