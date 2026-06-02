---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 21 — TYPE CHECKING & CONVERSION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Type Checking & Conversion">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Type <span class="highlight">Checking</span> &amp; <span class="highlight">Conversion</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="section-label">Checking Data Types</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:2;">
    <span style="color:#0e6ead;">x</span> = <span style="color:#b45309;">42</span><br>
    <span style="color:#0e6ead;">y</span> = <span style="color:#2d7a00;">"hello"</span><br>
    <span style="color:#0e6ead;">z</span> = [<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">x</span>))   <span style="color:#6b7280;"># &lt;class 'int'&gt;</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">y</span>))   <span style="color:#6b7280;"># &lt;class 'str'&gt;</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">isinstance</span>(<span style="color:#0e6ead;">z</span>, <span style="color:#ef5050;">list</span>)) <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Type Conversion (Casting)</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:2;">
    <span style="color:#0e6ead;">a</span> = <span style="color:#ef5050;">int</span>(<span style="color:#2d7a00;">"42"</span>)    <span style="color:#6b7280;"># str → int  : 42</span><br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#ef5050;">float</span>(<span style="color:#b45309;">5</span>)    <span style="color:#6b7280;"># int → float: 5.0</span><br>
    <span style="color:#0e6ead;">c</span> = <span style="color:#ef5050;">str</span>(<span style="color:#b45309;">99</span>)     <span style="color:#6b7280;"># int → str  : "99"</span><br>
    <span style="color:#0e6ead;">d</span> = <span style="color:#ef5050;">list</span>((<span style="color:#b45309;">1</span>,<span style="color:#b45309;">2</span>)) <span style="color:#6b7280;"># tuple → list</span><br>
    <span style="color:#0e6ead;">e</span> = <span style="color:#ef5050;">bool</span>(<span style="color:#b45309;">0</span>)    <span style="color:#6b7280;"># int → bool : False</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Conversion Flow Diagram</div>

  <div style="display:flex;flex-direction:column;gap:6px;">
    <div style="display:flex;align-items:center;gap:6px;" v-click>
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:#2b6cb0;min-width:60px;text-align:center;">"42"</div>
      <div style="font-size:.65rem;color:var(--muted);">str</div>
      <div style="color:var(--muted);">→ int() →</div>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);">42</div>
      <div style="font-size:.65rem;color:var(--muted);">int</div>
    </div>
    <div style="display:flex;align-items:center;gap:6px;" v-click>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">5</div>
      <div style="font-size:.65rem;color:var(--muted);">int</div>
      <div style="color:var(--muted);">→ float() →</div>
      <div style="background:#f0fff4;border:1px solid var(--green);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--green);">5.0</div>
      <div style="font-size:.65rem;color:var(--muted);">float</div>
    </div>
    <div style="display:flex;align-items:center;gap:6px;" v-click>
      <div style="background:var(--red-soft);border:1px solid var(--red);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:var(--red-dark);min-width:60px;text-align:center;">99</div>
      <div style="font-size:.65rem;color:var(--muted);">int</div>
      <div style="color:var(--muted);">→ str() →</div>
      <div style="background:#ebf8ff;border:1px solid var(--blue);border-radius:6px;padding:5px 12px;font-family:'Fira Code',monospace;font-size:.72rem;font-weight:700;color:#2b6cb0;">"99"</div>
      <div style="font-size:.65rem;color:var(--muted);">str</div>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:8px;">
    <div><strong>Invalid conversion raises ValueError!</strong> <span class="mono">int("hello")</span> → ValueError: invalid literal</div>
  </div>

  <div v-click class="card card-green" style="margin-top:6px;">
    <div class="small-text"><strong>Best practice:</strong> Wrap type conversions in <span class="mono">try/except</span> blocks to handle invalid inputs gracefully.</div>
  </div>
</div>
</div>

  </template>
</Slide2>
