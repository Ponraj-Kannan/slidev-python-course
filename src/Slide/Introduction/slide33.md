---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 14 — SEQUENCE TYPE: list
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Sequence Type — <span class="highlight">list</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">list</strong> stores an <strong>ordered, mutable collection</strong> of items. Items can be of different types. Defined using square brackets <span class="mono">[ ]</span>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">fruits</span> = [<span style="color:#2d7a00;">"apple"</span>, <span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"cherry"</span>]<br>
    <span style="color:#0e6ead;">scores</span> = [<span style="color:#b45309;">85</span>, <span style="color:#b45309;">92</span>, <span style="color:#b45309;">78</span>, <span style="color:#b45309;">95</span>]<br>
    <span style="color:#0e6ead;">mixed</span>  = [<span style="color:#b45309;">1</span>, <span style="color:#2d7a00;">"hello"</span>, <span style="color:#ef5050;">True</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fruits</span>[<span style="color:#b45309;">0</span>])  <span style="color:#6b7280;"># apple</span><br>
    <span style="color:#0e6ead;">fruits</span>[<span style="color:#b45309;">1</span>] = <span style="color:#2d7a00;">"mango"</span> <span style="color:#6b7280;"># mutable!</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">List Index Visualization</div>
    <div style="display:flex;gap:3px;align-items:center;flex-wrap:wrap;">
      <div style="text-align:center;"><div style="background:var(--red-soft);border:2px solid var(--red);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);font-size:.72rem;">"apple"</div><div style="font-size:.55rem;color:var(--muted);">index 0</div></div>
      <div style="text-align:center;"><div style="background:#f0fff4;border:2px solid var(--green);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);font-size:.72rem;">"banana"</div><div style="font-size:.55rem;color:var(--muted);">index 1</div></div>
      <div style="text-align:center;"><div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.72rem;">"cherry"</div><div style="font-size:.55rem;color:var(--muted);">index 2</div></div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common List Operations</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#0e6ead;">nums</span> = [<span style="color:#b45309;">3</span>, <span style="color:#b45309;">1</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">1</span>, <span style="color:#b45309;">5</span>]<br>
    <span style="color:#0e6ead;">nums</span>.append(<span style="color:#b45309;">9</span>)   <span style="color:#6b7280;"># add to end</span><br>
    <span style="color:#0e6ead;">nums</span>.remove(<span style="color:#b45309;">1</span>)   <span style="color:#6b7280;"># remove first 1</span><br>
    <span style="color:#0e6ead;">nums</span>.sort()       <span style="color:#6b7280;"># sort in place</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">nums</span>))  <span style="color:#6b7280;"># 5</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">nums</span>[<span style="color:#b45309;">-1</span>])   <span style="color:#6b7280;"># last element</span>
  </div>

  <div style="margin-top:6px;">
    <table class="cmp-table" style="font-size:.68rem;">
      <thead v-click><tr><th>Feature</th><th>list</th></tr></thead>
      <tbody>
        <tr v-click><td>Ordered</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Mutable (changeable)</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Allows duplicates</td><td class="yes">Yes</td></tr>
        <tr v-click><td>Mixed types allowed</td><td class="yes">Yes</td></tr>
      </tbody>
    </table>
  </div>

</div>

</div>

  </template>
</Slide2>
