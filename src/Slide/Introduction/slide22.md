---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 8 — CASE SENSITIVITY & RESERVED KEYWORDS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Variable Naming Rules">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Case Sensitivity</span> &amp; Reserved <span class="highlight">Keywords</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      Python is <strong style="color:var(--red);">case-sensitive</strong>. <span class="mono">Name</span>, <span class="mono">name</span>, and <span class="mono">NAME</span> are <strong>three different variables</strong>.
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;margin-top:4px;">
    <span style="color:#0e6ead;">name</span> = <span style="color:#2d7a00;">"Alice"</span><br>
    <span style="color:#c49a00;">Name</span> = <span style="color:#2d7a00;">"Bob"</span><br>
    <span style="color:#ef5050;">NAME</span> = <span style="color:#2d7a00;">"Charlie"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span>, <span style="color:#c49a00;">Name</span>, <span style="color:#ef5050;">NAME</span>)
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">Alice &nbsp; Bob &nbsp; Charlie</div>

  <div v-click class="callout callout-warn" style="margin-top:4px;">
    <div><strong>Beginner Trap:</strong> Writing <span class="mono">Print()</span> instead of <span class="mono" style="color:var(--green);">print()</span> gives a NameError because Python is case-sensitive!</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Python Reserved Keywords</div>
  <div v-click class="small-text" style="margin-bottom:6px;">These cannot be used as variable names</div>

  <div style="display:flex;gap:4px;flex-wrap:wrap;">
    <span v-click style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">False</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">True</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">None</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">and</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">or</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">not</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">if</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">elif</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">else</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">for</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">while</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">break</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">continue</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">pass</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">def</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">class</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">return</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">import</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">from</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">in</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">is</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">lambda</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">try</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">except</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">with</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">del</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">global</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">yield</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">raise</span>
    <span v-after style="background:var(--red-soft);color:var(--red-dark);border:1px solid var(--red);border-radius:6px;padding:3px 10px;font-family:'Fira Code',monospace;font-size:.68rem;font-weight:700;">assert</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:8px;">
    <div>Run <span class="mono">help("keywords")</span> in Python to see the full list of all reserved keywords.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
