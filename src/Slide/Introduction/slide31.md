---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 13 — SEQUENCE TYPE: str
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Sequence Type — <span class="highlight">str</span> (String)</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">str</strong> stores a <strong>sequence of characters</strong> — text enclosed in single (<span class="mono">'</span>) or double (<span class="mono">"</span>) quotes.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">name</span>     = <span style="color:#2d7a00;">"Python"</span><br>
    <span style="color:#0e6ead;">greeting</span> = <span style="color:#2d7a00;">'Hello!'</span><br>
    <span style="color:#0e6ead;">multi</span>    = <span style="color:#2d7a00;">"""Line 1<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Line 2"""</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span>[<span style="color:#b45309;">0</span>])   <span style="color:#6b7280;"># P</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">name</span>)) <span style="color:#6b7280;"># 6</span>
  </div>

  <div v-click class="section-label" style="margin-top:4px;">Character Index Visualization</div>
  <div v-after style="display:flex;gap:3px;flex-wrap:wrap;">
    <div v-click style="text-align:center;">
      <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);font-size:.85rem;">P</div>
      <div style="font-size:.55rem;color:var(--muted);">0</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.85rem;">y</div>
      <div style="font-size:.55rem;color:var(--muted);">1</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:#f0fff4;border:2px solid var(--green);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--green);font-size:.85rem;">t</div>
      <div style="font-size:.55rem;color:var(--muted);">2</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:#fffaf0;border:2px solid var(--orange);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--orange);font-size:.85rem;">h</div>
      <div style="font-size:.55rem;color:var(--muted);">3</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:var(--red-soft);border:2px solid var(--red);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:var(--red-dark);font-size:.85rem;">o</div>
      <div style="font-size:.55rem;color:var(--muted);">4</div>
    </div>
    <div v-after style="text-align:center;">
      <div style="background:#ebf8ff;border:2px solid var(--blue);border-radius:6px;padding:6px 10px;font-family:'Fira Code',monospace;font-weight:700;color:#2b6cb0;font-size:.85rem;">n</div>
      <div style="font-size:.55rem;color:var(--muted);">5</div>
    </div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">Common String Operations</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Hello World"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.upper())    <span style="color:#6b7280;"># HELLO WORLD</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.lower())    <span style="color:#6b7280;"># hello world</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>:<span style="color:#b45309;">5</span>])     <span style="color:#6b7280;"># Hello</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.replace(<span style="color:#2d7a00;">"World"</span>, <span style="color:#2d7a00;">"Python"</span>))<br>
    <span style="color:#6b7280;"># Hello Python</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Strings are <strong>immutable</strong> — you cannot change a character in-place. You must create a new string.</div>
  </div>

  <div v-click class="card card-orange">
    <div class="small-text"><strong>Real-world use:</strong> Names, messages, file paths, user input, text processing</div>
  </div>

</div>

</div>

  </template>
</Slide2>
