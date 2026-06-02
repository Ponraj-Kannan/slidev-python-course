---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — SEQUENCE TYPE: tuple
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Sequence Type — <span class="highlight">tuple</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">tuple</strong> stores an <strong>ordered, immutable collection</strong> of items. Once created, the values <strong>cannot be changed</strong>. Defined using parentheses <span class="mono">( )</span>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">coords</span>  = (<span style="color:#b45309;">10.5</span>, <span style="color:#b45309;">20.3</span>)<br>
    <span style="color:#0e6ead;">rgb</span>     = (<span style="color:#b45309;">255</span>, <span style="color:#b45309;">128</span>, <span style="color:#b45309;">0</span>)<br>
    <span style="color:#0e6ead;">single</span>  = (<span style="color:#b45309;">42</span>,)   <span style="color:#6b7280;"># note trailing comma</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">coords</span>[<span style="color:#b45309;">0</span>])  <span style="color:#6b7280;"># 10.5</span><br>
    <span style="color:#6b7280;"># coords[0] = 5  → TypeError!</span>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:4px;">
    <div>Tuples are <strong>immutable</strong> — any attempt to modify them raises a <span class="mono">TypeError</span>. This is intentional and useful!</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">list vs tuple Comparison</div>

  <div >
    <table class="cmp-table">
      <thead>
        <tr v-click><th>Feature</th><th>list</th><th>tuple</th></tr>
      </thead>
      <tbody>
        <tr v-click><td>Syntax</td><td class="mono">[ ]</td><td class="mono">( )</td></tr>
        <tr v-click><td>Mutable</td><td class="yes">Yes</td><td class="no">No</td></tr>
        <tr v-click><td>Ordered</td><td class="yes">Yes</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Allows duplicates</td><td class="yes">Yes</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Speed</td><td>Slower</td><td class="yes">Faster</td></tr>
        <tr v-click><td>Use case</td><td>Dynamic data</td><td>Fixed data</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click style="margin-top:8px;">
    <div class="section-label" style="margin-bottom:6px;">Tuple Memory Visualization</div>
    <div style="display:flex;gap:3px;align-items:center;">
      <div style="text-align:center;"><div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.78rem;">10.5</div><div style="font-size:.55rem;color:var(--muted);">[0] 🔒</div></div>
      <div style="text-align:center;"><div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 12px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.78rem;">20.3</div><div style="font-size:.55rem;color:var(--muted);">[1] 🔒</div></div>
      <div style="font-size:.68rem;color:var(--red-dark);font-weight:700;margin-left:6px;">immutable</div>
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
