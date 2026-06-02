---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 9 — range(start, stop, step) IN DETAIL
═══════════════════════════════════════════════════════ -->

<Slide2 topic="For Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">range()</span> — start, stop, step</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Full Syntax</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px;font-family:'Fira Code',monospace;font-size:.76rem;line-height:2;">
    <span style="color:#2d7a00;">range</span>(<span style="color:#ef5050;">start</span>, <span style="color:#b45309;">stop</span>, <span style="color:#0e6ead;">step</span>)
  </div>

  <div v-click style="margin-top:8px;display:flex;flex-direction:column;gap:5px;">
    <div class="card" style="padding:8px 14px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-keyword">start</span>
        <span class="body-text">Where to begin (default: 0)</span>
      </div>
    </div>
    <div class="card" style="padding:8px 14px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-value">stop</span>
        <span class="body-text">Where to end (not included)</span>
      </div>
    </div>
    <div class="card" style="padding:8px 14px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-operator">step</span>
        <span class="body-text">How much to jump (default: 1)</span>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Step can be <strong>negative</strong> to count backwards! <span class="mono">range(10, 0, -1)</span></div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Examples with Visualization</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#6b7280;"># Step = 2 (even numbers)</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">0</span>, <span style="color:#b45309;">10</span>, <span style="color:#b45309;">2</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#6b7280;"># 0 2 4 6 8</span><br><br>
    <span style="color:#6b7280;"># Countdown (negative step)</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">5</span>, <span style="color:#b45309;">0</span>, <span style="color:#b45309;">-1</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#6b7280;"># 5 4 3 2 1</span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Step=2 Visualization: range(0,10,2)</div>
    <div style="background:#f7f8fc;border-radius:8px;padding:8px 12px;border:1px solid var(--border);display:flex;gap:4px;flex-wrap:wrap;align-items:center;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">0</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">2</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">4</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">6</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 8px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">8</div>
      <div style="color:var(--muted);font-size:.7rem;font-weight:700;">+2</div>
      <div style="background:#e2e8f0;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:var(--muted)">10 = stop</div>
    </div>
  </div>
</div>
</div>
  </template>
</Slide2>
