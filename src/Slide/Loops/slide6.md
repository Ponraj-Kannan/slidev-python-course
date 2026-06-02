---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 7 — FOR LOOP: SYNTAX + STRING ITERATION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="For Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">For</span> Loop — Syntax &amp; Iterating Strings</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Syntax Structure</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px;font-family:'Fira Code',monospace;font-size:.8rem;line-height:2;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">variable</span> <span style="color:#ef5050;">in</span> <span style="color:#c49a00;">sequence</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;color:#2d7a00;">body of loop</span>
  </div>

  <div v-click style="margin-top:6px;display:flex;flex-direction:column;gap:6px;  border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-keyword">for</span>
      <span class="body-text">Loop keyword</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-varname">variable</span>
      <span class="body-text">Takes each item from the sequence</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-keyword">in</span>
      <span class="body-text">Membership operator — part of for syntax</span>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="syn-value">sequence</span>
      <span class="body-text">String, list, range, tuple etc.</span>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;">
    <div>The <span class="mono">for</span> loop automatically stops when all items in the sequence are exhausted. No need to update a counter!</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">Iterating Through a String</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.75rem;line-height:1.9;">
    <span style="color:#6b7280;"># Each character of the string</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">"Python"</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">ch</span>)</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Iteration Visualization</div>
    <div style="display:flex;gap:4px;flex-wrap:wrap;">
      <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:var(--red-dark);">P</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=0</div>
      </div>
      <div v-after style="background:#ebf8ff;border:2px solid #3182ce;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#2b6cb0;">y</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=1</div>
      </div>
      <div v-after style="background:#f0fff4;border:2px solid #38a169;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#276749;">t</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=2</div>
      </div>
      <div v-after style="background:#fffaf0;border:2px solid #dd6b20;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#c05621;">h</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=3</div>
      </div>
      <div v-after style="background:#fde8e8;border:2px solid #ef5050;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#c73c3c;">o</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=4</div>
      </div>
      <div v-after style="background:#ebf8ff;border:2px solid #3182ce;border-radius:8px;padding:8px 12px;text-align:center;min-width:38px;">
        <div class="mono" style="font-size:.85rem;font-weight:700;color:#2b6cb0;">n</div>
        <div style="font-size:.55rem;color:var(--muted);">ch=5</div>
      </div>
    </div>
  </div>

  <div v-click class="output-box" style="margin-top:8px;font-size:.72rem;">
    P &nbsp;y &nbsp;t &nbsp;h &nbsp;o &nbsp;n
  </div>
</div>

</div>

  </template>
</Slide2>
