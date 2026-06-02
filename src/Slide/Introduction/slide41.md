---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 18 — DICTIONARY TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Dictionary Type — <span class="highlight">dict</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">dict</strong> stores data as <strong>key-value pairs</strong>. Keys must be unique. Access values using their key — like a real dictionary where a word is the key and definition is the value.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">student</span> = {<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"name"</span>: <span style="color:#2d7a00;">"Alice"</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"age"</span>:  <span style="color:#b45309;">21</span>,</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"marks"</span>: <span style="color:#b45309;">95.5</span></span>
    }<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">student</span>[<span style="color:#2d7a00;">"name"</span>])  <span style="color:#6b7280;"># Alice</span>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Key-Value Visualization</div>
  <div v-after style="display:flex;flex-direction:column;gap:4px;">
    <div style="display:flex;align-items:center;gap:8px;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">"name"</div>
      <div style="color:var(--muted);font-weight:700;">→</div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--green);">"Alice"</div>
    </div>
    <div style="display:flex;align-items:center;gap:8px;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">"age"</div>
      <div style="color:var(--muted);font-weight:700;">→</div>
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:#2b6cb0;">21</div>
    </div>
    <div style="display:flex;align-items:center;gap:8px;">
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">"marks"</div>
      <div style="color:var(--muted);font-weight:700;">→</div>
      <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--orange);">95.5</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common dict Operations</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#6b7280;"># Add / update</span><br>
    <span style="color:#0e6ead;">student</span>[<span style="color:#2d7a00;">"grade"</span>] = <span style="color:#2d7a00;">"A"</span><br>
    <span style="color:#6b7280;"># Delete</span><br>
    <span style="color:#ef5050;">del</span> <span style="color:#0e6ead;">student</span>[<span style="color:#2d7a00;">"age"</span>]<br>
    <span style="color:#6b7280;"># Check key exists</span><br>
    <span style="color:#2d7a00;">"name"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">student</span>  <span style="color:#6b7280;"># True</span><br>
    <span style="color:#6b7280;"># Iterate</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">k</span>, <span style="color:#0e6ead;">v</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">student</span>.items():<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">k</span>, <span style="color:#2d7a00;">"→"</span>, <span style="color:#0e6ead;">v</span>)</span>
  </div>

  <div style="margin-top:6px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Feature</th><th>dict</th></tr></thead>
      <tbody>
        <tr v-click><td>Ordered (Python 3.7+)</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Mutable</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Duplicate keys</td><td class="no">No</td></tr>
        <tr v-click><td>Duplicate values</td><td class="yes">Yes</td></tr>
      </tbody>
    </table>
  </div>
</div>

</div>

  </template>
</Slide2>
