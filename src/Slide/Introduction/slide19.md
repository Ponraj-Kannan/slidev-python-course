---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 6 — DELETING & SWAPPING VARIABLES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Variables">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Deleting</span> &amp; <span class="highlight">Swapping</span> Variables</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-red">Deleting a Variable — del</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">x</span> = <span style="color:#b45309;">10</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>) <span style="color:#6b7280;"># 10</span><br>
    <span style="color:#ef5050;">del</span> <span style="color:#0e6ead;">x</span>    <span style="color:#6b7280;"># removes the variable</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>) <span style="color:#6b7280;"># NameError!</span>
  </div>

  <div v-click class="callout callout-danger">
    <div>After <span class="mono" style="color:var(--red-dark);">del x</span>, accessing <span class="mono">x</span> raises a <strong>NameError</strong> — the name no longer exists in memory.</div>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Memory After del</div>
    <div style="display:flex;gap:12px;align-items:center;">
      <div class="mem-box" style="flex:1;">
        <div class="mem-header">Before del x</div>
        <div class="mem-row">
          <div class="mem-name">x</div>
          <div class="mem-val">10</div>
          <div class="mem-type">int</div>
        </div>
      </div>
      <div style="font-size:1.4rem;color:var(--muted);">→</div>
      <div class="mem-box" style="flex:1;">
        <div class="mem-header">After del x</div>
        <div class="mem-row">
          <div style="padding:8px 12px;font-size:.68rem;color:var(--muted);font-style:italic;flex:1;">x is gone — NameError</div>
        </div>
      </div>
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-green">Swapping Variables</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">a</span> = <span style="color:#b45309;">5</span><br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#b45309;">10</span><br>
    <span style="color:#6b7280;"># Python's elegant one-liner swap</span><br>
    <span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span> = <span style="color:#0e6ead;">b</span>, <span style="color:#0e6ead;">a</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span>, <span style="color:#0e6ead;">b</span>) <span style="color:#6b7280;"># 10  5</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">10 &nbsp; 5</div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Swap Visualization</div>
    <div style="display:flex;gap:8px;align-items:center;flex-wrap:wrap;">
      <div style="text-align:center;">
        <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:8px;padding:8px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">a = 5</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">Before</div>
      </div>
      <div style="font-size:1.2rem;color:var(--muted);">⇄</div>
      <div style="text-align:center;">
        <div style="background:#f0fff4;border:2px solid var(--green);border-radius:8px;padding:8px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">b = 10</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">Before</div>
      </div>
      <div style="color:var(--muted);font-size:1rem;font-weight:700;">→</div>
      <div style="text-align:center;">
        <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:8px;padding:8px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">a = 10</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">After</div>
      </div>
      <div style="font-size:1.2rem;color:var(--muted);">⇄</div>
      <div style="text-align:center;">
        <div style="background:#f0fff4;border:2px solid var(--green);border-radius:8px;padding:8px 14px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">b = 5</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">After</div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;">
    <div>Python's tuple unpacking makes swapping <strong>a single line</strong> — no temporary variable needed, unlike other languages!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
