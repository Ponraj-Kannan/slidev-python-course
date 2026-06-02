---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 8 — FOR LOOP: LIST ITERATION + RANGE()
═══════════════════════════════════════════════════════ -->

<Slide2 topic="For Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">For</span> Loop — Lists &amp; <span class="highlight">range()</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Iterating Through a List</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.75rem;line-height:1.9;">
    <span style="color:#6b7280;"># Loop through a list</span><br>
    <span style="color:#0e6ead;">fruits</span> = [<span style="color:#2d7a00;">"apple"</span>, <span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"cherry"</span>]<br>
    <br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">fruit</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">fruits</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"I like"</span>, <span style="color:#0e6ead;">fruit</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    I like apple<br>
    I like banana<br>
    I like cherry
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">List Iteration Visual</div>
    <div style="display:flex;gap:4px;align-items:center;flex-wrap:wrap;  border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
      <div style="background:#ebf8ff;border:2px solid #3182ce;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:#2b6cb0;">apple</div>
      <div style="color:var(--muted);font-size:1rem;">&#x2192;</div>
      <div style="background:#f0fff4;border:2px solid #38a169;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:#276749;">banana</div>
      <div style="color:var(--muted);font-size:1rem;">&#x2192;</div>
      <div style="background:#fde8e8;border:2px solid #ef5050;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:#c73c3c;">cherry</div>
      <div style="color:var(--muted);font-size:1rem;">&#x2192;</div>
      <div style="background:#e2e8f0;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:var(--muted)">Done</div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">range() Function</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># range(stop) — 0 to stop-1</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">5</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#6b7280;"># Output: 0 1 2 3 4</span><br><br>
    <span style="color:#6b7280;"># range(start, stop)</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
    <span style="color:#6b7280;"># Output: 1 2 3 4 5</span>
  </div>

  <div style="margin-top:6px;">
    <div v-click class="section-label" style="margin-bottom:6px;">range() Sequence Visualization</div>
    <div v-after style="background:#f7f8fc;border-radius:8px;padding:8px 12px;border:1px solid var(--border);">
      <div style="font-size:.65rem;color:var(--muted);margin-bottom:4px;font-family:'Fira Code',monospace;">range(1, 6) generates:</div>
      <div style="display:flex;gap:6px;">
        <div v-click style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">1</div>
        <div v-after style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">2</div>
        <div v-after style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">3</div>
        <div v-after style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">4</div>
        <div v-after style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.8rem;font-weight:700;color:var(--red-dark);">5</div>
        <div v-after style="background:#e2e8f0;border-radius:8px;padding:6px 12px;font-size:.7rem;font-weight:700;color:var(--muted)">stop</div>
      </div>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
