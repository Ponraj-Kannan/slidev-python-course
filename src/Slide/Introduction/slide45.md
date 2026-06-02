---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 20 — DATA TYPE COMPARISON TABLE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Data Type <span class="highlight">Comparison</span> &amp; Hierarchy</div>

<div class="flex-col" style="gap:12px;">

  <div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead>
        <tr><th>Type</th><th>Category</th><th>Mutable</th><th>Ordered</th><th>Duplicates</th><th>Example</th></tr>
      </thead>
      <tbody>
        <tr v-click><td><span class="pill pill-red" style="font-size:.6rem;padding:2px 8px;">int</span></td><td>Numeric</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">42</td></tr>
        <tr v-click><td><span class="pill pill-blue" style="font-size:.6rem;padding:2px 8px;">float</span></td><td>Numeric</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">3.14</td></tr>
        <tr v-click><td><span class="pill" style="background:#fffaf0;color:var(--orange);font-size:.6rem;padding:2px 8px;">complex</span></td><td>Numeric</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">2+3j</td></tr>
        <tr v-click><td><span class="pill pill-navy" style="font-size:.6rem;padding:2px 8px;">str</span></td><td>Sequence</td><td class="no">No</td><td class="yes">Yes</td><td class="yes">Yes</td><td class="mono" style="color:var(--green);">"hi"</td></tr>
        <tr v-click><td><span class="pill pill-green" style="font-size:.6rem;padding:2px 8px;">list</span></td><td>Sequence</td><td class="yes">Yes</td><td class="yes">Yes</td><td class="yes">Yes</td><td class="mono" style="color:var(--green);">[1,2]</td></tr>
        <tr v-click><td><span class="pill pill-blue" style="font-size:.6rem;padding:2px 8px;">tuple</span></td><td>Sequence</td><td class="no">No</td><td class="yes">Yes</td><td class="yes">Yes</td><td class="mono" style="color:var(--green);">(1,2)</td></tr>
        <tr v-click><td><span class="pill pill-green" style="font-size:.6rem;padding:2px 8px;">bool</span></td><td>Boolean</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">True</td></tr>
        <tr v-click><td><span class="pill pill-orange" style="font-size:.6rem;padding:2px 8px;">set</span></td><td>Set</td><td class="yes">Yes</td><td class="no">No</td><td class="no">No</td><td class="mono" style="color:var(--green);">{1,2}</td></tr>
        <tr v-click><td><span class="pill pill-navy" style="font-size:.6rem;padding:2px 8px;">dict</span></td><td>Mapping</td><td class="yes">Yes</td><td class="yes">Yes</td><td>Keys: No</td><td class="mono" style="color:var(--green);">{"k":v}</td></tr>
        <tr v-click><td><span class="pill" style="background:#f0e6ff;color:#6b21a8;font-size:.6rem;padding:2px 8px;">None</span></td><td>NoneType</td><td class="no">No</td><td>—</td><td>—</td><td class="mono" style="color:var(--green);">None</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:8px;">Type Hierarchy Visual</div>
    <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center;">
      <div style="background:#f0f4ff;border:1px solid #c5cde8;border-radius:10px;padding:8px 14px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;margin-bottom:4px;">NUMERIC</div>
        <div style="display:flex;gap:4px;">
          <span class="pill pill-red" style="font-size:.6rem;padding:2px 8px;">int</span>
          <span class="pill pill-blue" style="font-size:.6rem;padding:2px 8px;">float</span>
          <span class="pill pill-orange" style="font-size:.6rem;padding:2px 8px;">complex</span>
        </div>
      </div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:10px;padding:8px 14px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;margin-bottom:4px;">SEQUENCE</div>
        <div style="display:flex;gap:4px;">
          <span class="pill pill-navy" style="font-size:.6rem;padding:2px 8px;">str</span>
          <span class="pill pill-green" style="font-size:.6rem;padding:2px 8px;">list</span>
          <span class="pill pill-blue" style="font-size:.6rem;padding:2px 8px;">tuple</span>
        </div>
      </div>
      <div style="background:#fffaf0;border:1px solid var(--orange);border-radius:10px;padding:8px 14px;text-align:center;">
        <div style="font-size:.62rem;color:var(--muted);font-weight:700;margin-bottom:4px;">OTHER</div>
        <div style="display:flex;gap:4px;">
          <span class="pill pill-green" style="font-size:.6rem;padding:2px 8px;">bool</span>
          <span class="pill pill-orange" style="font-size:.6rem;padding:2px 8px;">set</span>
          <span class="pill pill-navy" style="font-size:.6rem;padding:2px 8px;">dict</span>
          <span class="pill" style="background:#f0e6ff;color:#6b21a8;font-size:.6rem;padding:2px 8px;">None</span>
        </div>
      </div>
    </div>
  </div>

</div>

  </template>
</Slide2>
