---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 27 — IDENTITY OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Identity <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Identity operators</strong> check whether two variables point to the <strong>same object in memory</strong> — not just whether their values are equal.
    </div>
  </div>

  <div v-click style="display:flex;flex-direction:column;gap:6px;margin-top:6px;">
    <div class="card-green" style="border-radius:8px;padding:12px 16px;">
      <div style="font-family:'Fira Code',monospace;font-size:.85rem;font-weight:800;color:var(--green);margin-bottom:4px;">is</div>
      <div style="font-size:.75rem;color:var(--slate);">Returns <span class="mono" style="color:var(--green);">True</span> if both variables refer to the <strong>same object</strong></div>
    </div>
    <div class="card-red" style="border-radius:8px;padding:12px 16px;">
      <div style="font-family:'Fira Code',monospace;font-size:.85rem;font-weight:800;color:var(--red-dark);margin-bottom:4px;">is not</div>
      <div style="font-size:.75rem;color:var(--slate);">Returns <span class="mono" style="color:var(--green);">True</span> if both variables refer to <strong>different objects</strong></div>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:6px;">
    <div><strong>Key difference:</strong> <span class="mono">==</span> checks <em>value equality</em>. <span class="mono">is</span> checks <em>object identity</em> (same memory address).</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Code Examples</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">a</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#0e6ead;">b</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#0e6ead;">c</span> = <span style="color:#0e6ead;">a</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> == <span style="color:#0e6ead;">b</span>)    <span style="color:#6b7280;"># True  (same values)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> <span style="color:#ef5050;">is</span> <span style="color:#0e6ead;">b</span>)    <span style="color:#6b7280;"># False (different objects)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> <span style="color:#ef5050;">is</span> <span style="color:#0e6ead;">c</span>)    <span style="color:#6b7280;"># True  (same object!)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> <span style="color:#ef5050;">is not</span> <span style="color:#0e6ead;">b</span>) <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Memory Diagram</div>
  <div v-after style="background:#f7f8fc;border-radius:10px;border:1px solid var(--border);padding:12px 14px;font-size:.72rem;">
    <div style="display:flex;gap:16px;align-items:center;flex-wrap:wrap;">
      <div style="text-align:center;">
        <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">a →</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">variable a</div>
      </div>
      <div style="text-align:center;">
        <div style="background:#f0fff4;border:2px solid var(--green);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);">[1,2,3]</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">object @ 0x1A</div>
      </div>
      <div style="font-size:1rem;color:var(--muted);">←</div>
      <div style="text-align:center;">
        <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);">← c</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">variable c</div>
      </div>
    </div>
    <div style="margin-top:10px;display:flex;gap:16px;align-items:center;">
      <div style="text-align:center;">
        <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">b →</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">variable b</div>
      </div>
      <div style="text-align:center;">
        <div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;">[1,2,3]</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:3px;">different object @ 0x2B</div>
      </div>
    </div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Best practice:</strong> Use <span class="mono">is</span> / <span class="mono">is not</span> to check for <span class="mono">None</span>: <span class="mono">if x is None:</span></div>
  </div>

</div>

</div>

  </template>
</Slide2>
