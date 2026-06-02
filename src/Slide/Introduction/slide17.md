---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 5 — MULTIPLE & SAME VALUE ASSIGNMENT + REASSIGNMENT
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Multiple</span> Assignment &amp; <span class="highlight">Reassignment</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-navy">Multiple Variable Assignment</span>
  </div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># Assign different values in one line</span><br>
    <span style="color:#0e6ead;">x</span>, <span style="color:#c49a00;">y</span>, <span style="color:#2d7a00;">z</span> <span style="color:#ef5050;">=</span> <span style="color:#b45309;">10</span>, <span style="color:#b45309;">20</span>, <span style="color:#b45309;">30</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>, <span style="color:#c49a00;">y</span>, <span style="color:#2d7a00;">z</span>) <span style="color:#6b7280;"># 10 20 30</span>
  </div>
  <div v-click class="output-box" style="font-size:.72rem;">10 &nbsp; 20 &nbsp; 30</div>

  <div v-click style="display:flex;gap:8px;align-items:center;margin-top:8px;">
    <span class="pill pill-green">Same Value to Multiple Variables</span>
  </div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># All three get the same value</span><br>
    <span style="color:#0e6ead;">a</span> = <span style="color:#c49a00;">b</span> = <span style="color:#2d7a00;">c</span> = <span style="color:#b45309;">100</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#c49a00;">b</span>, <span style="color:#2d7a00;">c</span>) <span style="color:#6b7280;"># 100 100 100</span>
  </div>
  <div v-click class="output-box" style="font-size:.72rem;">100 &nbsp; 100 &nbsp; 100</div>

</div>

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-red">Variable Reassignment</span>
  </div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">score</span> = <span style="color:#b45309;">50</span>   <span style="color:#6b7280;"># first assignment</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">score</span>) <span style="color:#6b7280;"># 50</span><br>
    <span style="color:#0e6ead;">score</span> = <span style="color:#b45309;">95</span>   <span style="color:#6b7280;"># reassignment</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">score</span>) <span style="color:#6b7280;"># 95</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Reassignment Memory Diagram</div>
    <div style="display:flex;gap:12px;align-items:flex-start;">
      <div style="flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);margin-bottom:4px;">Before</div>
        <div class="mem-box">
          <div class="mem-row">
            <div class="mem-name">score</div>
            <div class="mem-val">50</div>
          </div>
        </div>
      </div>
      <div style="font-size:1.4rem;color:var(--muted);padding-top:20px;">→</div>
      <div style="flex:1;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);margin-bottom:4px;">After score = 95</div>
        <div class="mem-box">
          <div class="mem-row">
            <div class="mem-name">score</div>
            <div class="mem-val" style="color:var(--orange);">95</div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Python can also <strong>change the type</strong> on reassignment: <span class="mono">x = 5</span> then <span class="mono">x = "hello"</span> is perfectly valid!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
