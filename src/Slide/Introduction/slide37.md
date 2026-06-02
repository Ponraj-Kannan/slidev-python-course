---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — BOOLEAN TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Boolean Type — <span class="highlight">bool</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">bool</strong> stores only <strong>two values</strong>: <span class="mono" style="color:var(--green);">True</span> or <span class="mono" style="color:var(--red-dark);">False</span>. Used for conditions and logical decisions.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">is_raining</span> = <span style="color:#ef5050;">True</span><br>
    <span style="color:#0e6ead;">is_adult</span>   = <span style="color:#b45309;">18</span> >= <span style="color:#b45309;">18</span>   <span style="color:#6b7280;"># True</span><br>
    <span style="color:#0e6ead;">is_even</span>    = <span style="color:#b45309;">7</span> % <span style="color:#b45309;">2</span> == <span style="color:#b45309;">0</span>  <span style="color:#6b7280;"># False</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">is_raining</span>)) <span style="color:#6b7280;"># &lt;class 'bool'&gt;</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">bool Visualization</div>
    <div style="display:flex;gap:12px;">
      <div style="background:#f0fff4;border:3px solid var(--green);border-radius:12px;padding:14px 24px;text-align:center;flex:1;">
        <div style="font-family:'Fira Code',monospace;font-size:1.2rem;font-weight:800;color:var(--green);">True</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:4px;">= 1 in int</div>
      </div>
      <div style="background:var(--red-soft);border:3px solid var(--red);border-radius:12px;padding:14px 24px;text-align:center;flex:1;">
        <div style="font-family:'Fira Code',monospace;font-size:1.2rem;font-weight:800;color:var(--red-dark);">False</div>
        <div style="font-size:.6rem;color:var(--muted);margin-top:4px;">= 0 in int</div>
      </div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Boolean in Conditions</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#0e6ead;">logged_in</span> = <span style="color:#ef5050;">True</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">logged_in</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Welcome back!"</span>)</span>
  </div>

  <div style="margin-top:8px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Value</th><th>bool(value)</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono">0, 0.0, "", None</td><td class="no">False</td></tr>
        <tr v-click><td class="mono">[], {}, ()</td><td class="no">False</td></tr>
        <tr v-click><td>Any non-zero number</td><td class="yes">True</td></tr>
        <tr v-click><td>Any non-empty string</td><td class="yes">True</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="card card-blue">
    <div class="small-text"><strong>Real-world use:</strong> Login state, flags, form validation, any yes/no decision</div>
  </div>

</div>

</div>

  </template>
</Slide2>
