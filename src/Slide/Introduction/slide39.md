---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 17 — SET TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Set Type — <span class="highlight">set</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">set</strong> stores an <strong>unordered collection of unique items</strong>. Duplicates are automatically removed. Defined with curly braces <span class="mono">{ }</span>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">colors</span> = {<span style="color:#2d7a00;">"red"</span>, <span style="color:#2d7a00;">"blue"</span>, <span style="color:#2d7a00;">"green"</span>}<br>
    <span style="color:#6b7280;"># Duplicates removed automatically</span><br>
    <span style="color:#0e6ead;">nums</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">nums</span>) <span style="color:#6b7280;"># {1, 2, 3, 4}</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">nums</span>)) <span style="color:#6b7280;"># &lt;class 'set'&gt;</span>
  </div>

  <div v-click style="margin-top:4px;">
    <div class="section-label" style="margin-bottom:6px;">Set Operations</div>
    <div style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">A</span> = {<span style="color:#b45309;">1</span>,<span style="color:#b45309;">2</span>,<span style="color:#b45309;">3</span>} &nbsp;<span style="color:#0e6ead;">B</span> = {<span style="color:#b45309;">3</span>,<span style="color:#b45309;">4</span>,<span style="color:#b45309;">5</span>}<br>
      <span style="color:#0e6ead;">A</span> | <span style="color:#0e6ead;">B</span> <span style="color:#6b7280;"># union: {1,2,3,4,5}</span><br>
      <span style="color:#0e6ead;">A</span> & <span style="color:#0e6ead;">B</span> <span style="color:#6b7280;"># intersection: {3}</span><br>
      <span style="color:#0e6ead;">A</span> - <span style="color:#0e6ead;">B</span> <span style="color:#6b7280;"># difference: {1,2}</span>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Set Uniqueness Visualization</div>

  <div v-after style="background:#f7f8fc;border-radius:10px;border:1px solid var(--border);padding:14px;">
    <div style="font-size:.65rem;color:var(--muted);margin-bottom:8px;font-family:'Fira Code',monospace;">Input: {1, 2, 2, 3, 3, 4}</div>
    <div style="display:flex;align-items:center;gap:6px;flex-wrap:wrap;margin-bottom:8px;">
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:#2b6cb0;">1</div>
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--red-dark);">2</div>
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--red-dark);">2 ✗</div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--green);">3</div>
      <div style="background:var(--red-soft);border:2px dashed var(--red);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--red-dark);">3 ✗</div>
      <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:5px;padding:4px 10px;font-family:'Fira Code',monospace;font-size:.75rem;font-weight:700;color:var(--orange);">4</div>
    </div>
    <div style="font-size:.7rem;color:var(--muted);">↓</div>
    <div style="font-size:.65rem;color:var(--muted);margin-top:4px;font-family:'Fira Code',monospace;">Result: {1, 2, 3, 4}  (duplicates removed)</div>
  </div>

  <div style="margin-top:8px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Feature</th><th>set</th></tr></thead>
      <tbody>
        <tr v-click><td>Ordered</td><td class="no">No</td></tr>
        <tr v-click><td>Allows duplicates</td><td class="no">No</td></tr>
        <tr v-click><td>Mutable</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Indexing</td><td class="no">No</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

  </template>
</Slide2>
