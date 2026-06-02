---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 19 — NONE TYPE
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">None Type — <span class="highlight">NoneType</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">None</strong> represents the <strong>absence of a value</strong> or a null/empty state. It is Python's way of saying "nothing here". There is only <strong>one</strong> None object in Python.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">result</span> = <span style="color:#ef5050;">None</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span>)          <span style="color:#6b7280;"># None</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">result</span>))    <span style="color:#6b7280;"># &lt;class 'NoneType'&gt;</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span> <span style="color:#ef5050;">is</span> <span style="color:#ef5050;">None</span>) <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;margin-top:4px;">
    None<br>
    &lt;class 'NoneType'&gt;<br>
    True
  </div>

  <div v-click class="callout callout-warn" style="margin-top:4px;">
    <div>Always use <span class="mono">x <strong>is</strong> None</span> (not <span class="mono">x == None</span>) to check for None. This is the Pythonic best practice.</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common Use Cases for None</div>

  <div style="display:flex;flex-direction:column;gap:6px;">
    <div v-click class="card" style="padding:10px 14px;">
      <div class="body-text"><strong>Function with no return value</strong></div>
      <div style="background:#f6f8fa;border-radius:6px;padding:8px;font-family:'Fira Code',monospace;font-size:.7rem;margin-top:6px;line-height:1.8;">
        <span style="color:#ef5050;">def</span> <span style="color:#2d7a00;">greet</span>():<br>
        <span style="padding-left:16px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Hello"</span>)</span>
        <span style="color:#0e6ead;">x</span> = <span style="color:#2d7a00;">greet</span>() <span style="color:#6b7280;"># x is None</span>
      </div>
    </div>
    <div v-click class="card" style="padding:10px 14px;">
      <div class="body-text"><strong>Default parameter / placeholder</strong></div>
      <div style="background:#f6f8fa;border-radius:6px;padding:8px;font-family:'Fira Code',monospace;font-size:.7rem;margin-top:6px;line-height:1.8;">
        <span style="color:#ef5050;">def</span> <span style="color:#2d7a00;">connect</span>(<span style="color:#0e6ead;">host</span>=<span style="color:#ef5050;">None</span>):<br>
        <span style="padding-left:16px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">host</span> <span style="color:#ef5050;">is</span> <span style="color:#ef5050;">None</span>:</span>
        <span style="padding-left:32px;display:block;"><span style="color:#0e6ead;">host</span> = <span style="color:#2d7a00;">"localhost"</span></span>
      </div>
    </div>
  </div>

  <div style="margin-top:8px;">
    <div v-click class="section-label" style="margin-bottom:6px;">None vs False vs 0</div>
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-after><tr><th>Value</th><th>bool()</th><th>Meaning</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:#6b21a8;">None</td><td class="no">False</td><td>No value at all</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);">False</td><td class="no">False</td><td>Explicitly false</td></tr>
        <tr v-click><td class="mono" style="color:var(--orange);">0</td><td class="no">False</td><td>Numeric zero</td></tr>
        <tr v-click><td class="mono" style="color:var(--green);">True</td><td class="yes">True</td><td>Explicitly true</td></tr>
      </tbody>
    </table>
  </div>

</div>

</div>

  </template>
</Slide2>
