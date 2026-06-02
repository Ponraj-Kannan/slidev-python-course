---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 26 — MEMBERSHIP OPERATORS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Membership <span class="highlight">Operators</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Membership operators</strong> test whether a value exists <strong>inside a sequence</strong> (list, tuple, string, set, or dict). They return <span class="mono" style="color:var(--green);">True</span> or <span class="mono" style="color:var(--red-dark);">False</span>.
    </div>
  </div>

  <div v-click style="display:flex;flex-direction:column;gap:6px;margin-top:6px;">
    <div class="card-green" style="border-radius:8px;padding:12px 16px;">
      <div style="font-family:'Fira Code',monospace;font-size:.85rem;font-weight:800;color:var(--green);margin-bottom:4px;">in</div>
      <div style="font-size:.75rem;color:var(--slate);">Returns <span class="mono" style="color:var(--green);">True</span> if the value <strong>is found</strong> in the sequence</div>
    </div>
    <div class="card-red" style="border-radius:8px;padding:12px 16px;">
      <div style="font-family:'Fira Code',monospace;font-size:.85rem;font-weight:800;color:var(--red-dark);margin-bottom:4px;">not in</div>
      <div style="font-size:.75rem;color:var(--slate);">Returns <span class="mono" style="color:var(--green);">True</span> if the value <strong>is NOT found</strong> in the sequence</div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Works on <span class="mono">list</span>, <span class="mono">tuple</span>, <span class="mono">str</span>, <span class="mono">set</span>, <span class="mono">dict</span> (checks keys), and <span class="mono">range</span>.</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Code Examples</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># With a list</span><br>
    <span style="color:#0e6ead;">fruits</span> = [<span style="color:#2d7a00;">"apple"</span>, <span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"cherry"</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"apple"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">fruits</span>)      <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"mango"</span> <span style="color:#ef5050;">not in</span> <span style="color:#0e6ead;">fruits</span>)  <span style="color:#6b7280;"># True</span><br><br>
    <span style="color:#6b7280;"># With a string</span><br>
    <span style="color:#0e6ead;">msg</span> = <span style="color:#2d7a00;">"Hello Python"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Python"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">msg</span>)         <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Java"</span> <span style="color:#ef5050;">not in</span> <span style="color:#0e6ead;">msg</span>)       <span style="color:#6b7280;"># True</span><br><br>
    <span style="color:#6b7280;"># With a dict (checks keys)</span><br>
    <span style="color:#0e6ead;">info</span> = {<span style="color:#2d7a00;">"name"</span>: <span style="color:#2d7a00;">"Alice"</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"name"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">info</span>)           <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Practical Use in a Loop</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:4px;">
    <span style="color:#0e6ead;">banned</span> = [<span style="color:#2d7a00;">"spam"</span>, <span style="color:#2d7a00;">"hack"</span>]<br>
    <span style="color:#0e6ead;">word</span> = <span style="color:#2d7a00;">"spam"</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">word</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">banned</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Word blocked!"</span>)</span>
  </div>

  <div v-click class="card card-green" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> Search features, filtering banned words, checking permissions, validating input choices</div>
  </div>

</div>

</div>

  </template>
</Slide2>
