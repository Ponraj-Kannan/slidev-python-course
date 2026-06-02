---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — break AND continue STATEMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Loop Control">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">break</span> &amp; <span class="highlight">continue</span> Statements</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click style="display:flex;align-items:center;gap:8px;margin-bottom:8px;">
    <span style="background:var(--red);color:#fff;border-radius:6px;padding:3px 12px;font-family:'Fira Code',monospace;font-weight:700;font-size:.85rem;">break</span>
    <span class="body-text">— Exits the loop immediately</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">10</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">i</span> == <span style="color:#b45309;">5</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">break</span> <span style="color:#6b7280;"># stop at 5</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; <span style="color:#c0392b;">(stopped before 5)</span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:4px;">break Flow Diagram</div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
      <div class="flow-node flow-start" style="width:120px;">for i in range</div>
      <div class="flow-arrow">&#x25BC;</div>
      <div class="flow-node flow-cond" style="width:140px;font-size:.68rem;">i == 5 ?</div>
      <div style="display:flex;gap:20px;">
        <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
          <div style="font-size:.6rem;color:var(--red);font-weight:700;">YES</div>
          <div class="flow-arrow">&#x25BC;</div>
          <div class="flow-node flow-end" style="width:80px;font-size:.65rem;">Exit Loop</div>
        </div>
        <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
          <div style="font-size:.6rem;color:var(--green);font-weight:700;">NO</div>
          <div class="flow-arrow">&#x25BC;</div>
          <div class="flow-node flow-body" style="width:90px;font-size:.65rem;">print(i)</div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click style="display:flex;align-items:center;gap:8px;margin-bottom:8px;">
    <span style="background:var(--green);color:#fff;border-radius:6px;padding:3px 12px;font-family:'Fira Code',monospace;font-weight:700;font-size:.85rem;">continue</span>
    <span class="body-text">— Skips current iteration</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">8</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">i</span> % <span style="color:#b45309;">2</span> == <span style="color:#b45309;">0</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">continue</span> <span style="color:#6b7280;"># skip even</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 3 &nbsp; 5 &nbsp; 7 &nbsp; <span style="color:#6b7280;">(even numbers skipped)</span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:4px;">continue Flow Diagram</div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
      <div class="flow-node flow-start" style="width:120px;">for i in range</div>
      <div class="flow-arrow">&#x25BC;</div>
      <div class="flow-node flow-cond" style="width:150px;font-size:.68rem;">i % 2 == 0 ?</div>
      <div style="display:flex;gap:20px;">
        <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
          <div style="font-size:.6rem;color:var(--red);font-weight:700;">YES</div>
          <div class="flow-arrow">&#x25BC;</div>
          <div class="flow-node" style="background:#fffaf0;border:1px solid var(--orange);color:var(--orange);width:90px;font-size:.65rem;">Skip → next i</div>
        </div>
        <div style="display:flex;flex-direction:column;align-items:center;gap:3px;">
          <div style="font-size:.6rem;color:var(--green);font-weight:700;">NO</div>
          <div class="flow-arrow">&#x25BC;</div>
          <div class="flow-node flow-body" style="width:90px;font-size:.65rem;">print(i)</div>
        </div>
      </div>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
