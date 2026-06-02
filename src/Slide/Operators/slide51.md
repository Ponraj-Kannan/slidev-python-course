---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 24 — LOGICAL OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Logical <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Logical operators</strong> combine multiple conditions to produce a single <strong>Boolean result</strong>. They are the backbone of decision-making in Python.
    </div>
  </div>

  <div v-click style="display:flex;flex-direction:column;gap:6px;margin-top:4px;">
    <div class="card-green" style="border-radius:8px;padding:10px 14px;">
      <div style="font-size:.72rem;font-weight:700;color:var(--green);margin-bottom:4px;font-family:'Fira Code',monospace;">and</div>
      <div style="font-size:.72rem;color:var(--slate);">Returns <span class="mono" style="color:var(--green);">True</span> only when <strong>both</strong> conditions are True</div>
    </div>
    <div class="card-blue" style="border-radius:8px;padding:10px 14px;">
      <div style="font-size:.72rem;font-weight:700;color:var(--blue);margin-bottom:4px;font-family:'Fira Code',monospace;">or</div>
      <div style="font-size:.72rem;color:var(--slate);">Returns <span class="mono" style="color:var(--green);">True</span> when <strong>at least one</strong> condition is True</div>
    </div>
    <div class="card-red" style="border-radius:8px;padding:10px 14px;">
      <div style="font-size:.72rem;font-weight:700;color:var(--red-dark);margin-bottom:4px;font-family:'Fira Code',monospace;">not</div>
      <div style="font-size:.72rem;color:var(--slate);"><strong>Reverses</strong> the Boolean value — True becomes False and vice versa</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Truth Table</div>

  <div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>A</th><th>B</th><th>A and B</th><th>A or B</th><th>not A</th></tr></thead>
      <tbody>
        <tr v-click><td class="yes">True</td><td class="yes">True</td><td class="yes">True</td><td class="yes">True</td><td class="no">False</td></tr>
        <tr v-click><td class="yes">True</td><td class="no">False</td><td class="no">False</td><td class="yes">True</td><td class="no">False</td></tr>
        <tr v-click><td class="no">False</td><td class="yes">True</td><td class="no">False</td><td class="yes">True</td><td class="yes">True</td></tr>
        <tr v-click><td class="no">False</td><td class="no">False</td><td class="no">False</td><td class="no">False</td><td class="yes">True</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Code Examples</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">age</span>, <span style="color:#0e6ead;">has_id</span> = <span style="color:#b45309;">20</span>, <span style="color:#ef5050;">True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">age</span> >= <span style="color:#b45309;">18</span> <span style="color:#ef5050;">and</span> <span style="color:#0e6ead;">has_id</span>)  <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">age</span> < <span style="color:#b45309;">16</span> <span style="color:#ef5050;">or</span> <span style="color:#0e6ead;">has_id</span>)   <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">not</span> <span style="color:#0e6ead;">has_id</span>)               <span style="color:#6b7280;"># False</span>
  </div>

  <div v-click class="card card-orange" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> Login with username AND password, access control, form validation with multiple fields</div>
  </div>

</div>

</div>

  </template>
</Slide2>
