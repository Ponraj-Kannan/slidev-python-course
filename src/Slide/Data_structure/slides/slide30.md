<Slide2 topic="Set Operations — Difference &amp; Symmetric">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Set Operations — <span class="highlight">Difference</span> &amp; <span class="highlight">Symmetric</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-red" style="text-align:center;">
    <div class="slide-h2" style="color:var(--red-dark);">Difference  -  A.difference(B)</div>
    <div class="small-text" style="margin-top:4px;">Items in A but not in B.</div>
  </div>

  <div v-click class="venn-wrap">
<svg viewBox="0 0 220 130" width="220" height="130">
  <circle cx="80" cy="65" r="55" fill="rgba(239,80,80,0.45)" stroke="#c73c3c" stroke-width="2"/>
  <circle cx="140" cy="65" r="55" fill="#ffffff" stroke="#2b6cb0" stroke-width="2"/>
  <path d="M 110 18 A 55 55 0 0 1 110 112 A 55 55 0 0 1 110 18 Z" fill="#ffffff" stroke="#2b6cb0" stroke-width="2"/>
  <text x="55" y="80" font-size="10" text-anchor="middle" font-family="'Fira Code',monospace" fill="#1a1f36d0" font-weight="700">A</text>
  <text x="165" y="80" font-size="10" text-anchor="middle" font-family="'Fira Code',monospace" fill="#1a1f36d0" font-weight="700">B</text>
</svg>
</div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">A</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>}<br>
    <span style="color:#0e6ead;">B</span> = {<span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">5</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">A</span> - <span style="color:#0e6ead;">B</span>)<br>
    <span style="color:#6b7280;"># {1, 2}</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-orange" style="text-align:center;">
    <div class="slide-h2" style="color:var(--orange);">Symmetric Difference  ^</div>
    <div class="small-text" style="margin-top:4px;">In A or B but NOT both.</div>
  </div>

  <div v-click class="venn-wrap">
<svg viewBox="0 0 220 130" width="220" height="130">
  <circle cx="80" cy="65" r="55" fill="rgba(221,107,32,0.45)" stroke="#c05621" stroke-width="2"/>
  <circle cx="140" cy="65" r="55" fill="rgba(221,107,32,0.45)" stroke="#c05621" stroke-width="2"/>
  <path d="M 110 18 A 55 55 0 0 1 110 112 A 55 55 0 0 1 110 18 Z" fill="#ffffff" stroke="#c05621" stroke-width="2"/>
<text x="55" y="80" font-size="10" text-anchor="middle" font-family="'Fira Code',monospace" fill="#1a1f36d0" font-weight="700">A</text>
  <text x="165" y="80" font-size="10" text-anchor="middle" font-family="'Fira Code',monospace" fill="#1a1f36d0" font-weight="700">B</text>
</svg>
</div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">A</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>}<br>
    <span style="color:#0e6ead;">B</span> = {<span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">5</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">A</span> ^ <span style="color:#0e6ead;">B</span>)<br>
    <span style="color:#6b7280;"># {1, 2, 4, 5}</span>
  </div>
</div>

</div>

<div v-click class="callout callout-info" style="margin-top:10px;font-size:.7rem;">
  <div>Each operator <span class="mono">| &amp; - ^</span> has a method form: <span class="mono">union, intersection, difference, symmetric_difference</span>.</div>
</div>

  </template>
</Slide2>
