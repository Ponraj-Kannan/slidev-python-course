---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 12 — NUMERIC TYPES: float & complex
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Data Types">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Numeric Types — <span class="highlight">float</span> &amp; <span class="highlight">complex</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-blue">float</span>
    <span class="body-text">Numbers with a decimal point</span>
  </div>

  <div v-after class="card-navy" style="border-radius:8px;font-size:.78rem;line-height:1.5;color:var(--slate);">
    Stores <strong>real numbers</strong> — numbers with a fractional part. Used for measurements, prices, and scientific values.
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:4px;">
    <span style="color:#0e6ead;">price</span>  = <span style="color:#b45309;">99.99</span><br>
    <span style="color:#0e6ead;">pi</span>     = <span style="color:#b45309;">3.14159</span><br>
    <span style="color:#0e6ead;">weight</span> = <span style="color:#b45309;">-4.5</span><br>
    <span style="color:#0e6ead;">sci</span>    = <span style="color:#b45309;">1.5e3</span>   <span style="color:#6b7280;"># = 1500.0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">pi</span>)) <span style="color:#6b7280;"># &lt;class 'float'&gt;</span>
  </div>

  <div v-click class="mem-box" style="margin-top:4px;">
    <div class="mem-header">float in Memory</div>
    <div class="mem-row">
      <div class="mem-name">price</div>
      <div class="mem-val">99.99</div>
      <div class="mem-type">float</div>
    </div>
  </div>

  <div v-click class="card card-green" style="margin-top:4px;">
    <div class="small-text"><strong>Real-world use:</strong> Prices, temperatures, GPS coordinates, scientific measurements</div>
  </div>

</div>

<div class="flex-col">

  <div v-click style="display:flex;gap:8px;align-items:center;margin-bottom:4px;">
    <span class="pill pill-orange">complex</span>
    <span class="body-text">Numbers with real + imaginary part</span>
  </div>

  <div v-after class="card-orange" style="border-radius:8px;font-size:.78rem;line-height:1.5;color:var(--slate);">
    Stores <strong>complex numbers</strong> in the form <span class="mono">a + bj</span>. Used in engineering, physics, and signal processing.
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:4px;">
    <span style="color:#0e6ead;">c2</span> = <span style="color:#b45309;">2</span> - <span style="color:#b45309;">1j</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">c1</span>.real)  <span style="color:#6b7280;"># 3.0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">c1</span>.imag)  <span style="color:#6b7280;"># 4.0</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">type</span>(<span style="color:#0e6ead;">c1</span>)) <span style="color:#6b7280;"># &lt;class 'complex'&gt;</span>
  </div>

  <div v-click style="margin-top:6px;">
    <div style="background:#f7f8fc;border-radius:8px;padding:10px 14px;border:1px solid var(--border);font-size:.72rem;">
      <div style="display:flex;gap:8px;align-items:center;font-family:'Fira Code',monospace;">
        <span style="background:var(--red-soft);color:var(--red-dark);border-radius:6px;padding:4px 12px;font-weight:700;">3</span>
        <span style="color:var(--muted);">+</span>
        <span style="background:#ebf8ff;color:#2b6cb0;border-radius:6px;padding:4px 12px;font-weight:700;">4j</span>
      </div>
      <div style="display:flex;gap:30px;margin-top:4px;">
        <div style="font-size:.6rem;color:var(--red-dark);font-weight:700;">Real part</div>
        <div style="font-size:.6rem;color:#2b6cb0;font-weight:700;">Imaginary part</div>
      </div>
    </div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px;">
    <div class="small-text"><strong>Real-world use:</strong> Signal processing, electrical engineering, physics simulations</div>
  </div>

</div>

</div>

  </template>
</Slide2>
