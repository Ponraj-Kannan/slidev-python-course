---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 4 — WHILE LOOP: SYNTAX + FLOWCHART
═══════════════════════════════════════════════════════ -->

<Slide2 topic="While Loop">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">While</span> Loop — Syntax &amp; Flow</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="section-label">Syntax Diagram</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:16px 18px;font-family:'Fira Code',monospace;font-size:.78rem;line-height:2;">
    <span style="color:#6b7280;"># Initialize variable</span><br>
    <span style="color:#0e6ead;">counter</span> = <span style="color:#b45309;">1</span><br>
    <span style="color:#ef5050;">while</span> <span style="color:#0e6ead;">counter</span> <span style="color:#c49a00;">&lt;=</span> <span style="color:#b45309;">5</span><span style="color:#1a1f36;">:</span><br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">counter</span>)</span>
    <span style="padding-left:20px;display:block;color:#6b7280;"># Update variable</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">counter</span> <span style="color:#c49a00;">+=</span> <span style="color:#b45309;">1</span></span>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Syntax Parts</div>
    <div style="display:flex;flex-direction:column;gap:4px;  border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-keyword">while</span>
        <span class="body-text">Keyword that starts the loop</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-value">condition</span>
        <span class="body-text">Boolean expression checked each time</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-varname">body</span>
        <span class="body-text">Indented block — runs while TRUE</span>
      </div>
      <div style="display:flex;gap:8px;align-items:center;">
        <span class="syn-operator">update</span>
        <span class="body-text">Change variable to avoid infinite loop</span>
      </div>
    </div>
  </div>

</div>

<div class="flex-col" >
  <div v-click class="section-label">Execution Flowchart</div>

  <div v-after style="display:flex;flex-direction:column;align-items:center;gap:4px;padding:10px 0;  border:1px solid #e1e4e8; padding: 10px; border-radius: 10px;">
    <div class="flow-node flow-start" style="width:140px;">START</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node" style="background:#ebf8ff;border:2px solid #3182ce;color:#2b6cb0;width:180px;font-size:.7rem;">Initialize: counter = 1</div>
    <div class="flow-arrow">&#x25BC;</div>
    <div class="flow-node flow-cond" style="width:180px;">counter &lt;= 5 ?</div>
    <div style="display:flex;align-items:flex-start;gap:16px;width:260px;">
      <div style="display:flex;flex-direction:column;align-items:center;gap:4px;margin-left:10px;">
        <div style="font-size:.6rem;color:var(--green);font-weight:700;">TRUE</div>
        <div class="flow-arrow">&#x25BC;</div>
        <div class="flow-node flow-body" style="width:110px;font-size:.65rem;">print(counter)<br>counter += 1</div>
        <div class="flow-arrow">&#x21B1;</div>
        <div style="font-size:.6rem;color:var(--muted);font-weight:700;text-align:center;">Back to<br>condition</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;gap:4px;padding-top:18px;">
        <div style="font-size:.6rem;color:var(--red);font-weight:700;">FALSE</div>
        <div class="flow-arrow">&#x25BC;</div>
        <div class="flow-node flow-end" style="width:80px;">END</div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:4px;">
    <div><strong>Always update</strong> the loop variable inside the body — otherwise the loop runs forever!</div>
  </div>
</div>

</div>

  </template>
</Slide2>
