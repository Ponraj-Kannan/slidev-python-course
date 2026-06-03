<Slide2 topic="Set Operations — Union &amp; Intersection">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Set Operations — <span class="highlight">Union</span> &amp; <span class="highlight">Intersection</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-red" style="text-align:center;">
    <div class="slide-h2" style="color:var(--red-dark);">Union  |  A.union(B)</div>
    <div class="small-text" style="margin-top:4px;">Everything in A or B (or both).</div>
  </div>

  <div v-click class="venn-wrap">
<svg viewBox="0 0 220 130" width="220" height="130">
  <circle cx="80" cy="65" r="55" fill="rgba(239,80,80,0.35)" stroke="#c73c3c" stroke-width="2"/>
  <circle cx="140" cy="65" r="55" fill="rgba(49,130,206,0.35)" stroke="#2b6cb0" stroke-width="2"/>
  <text x="55" y="80" font-size="10" text-anchor="middle" font-family="'Fira Code',monospace" fill="#1a1f36d0" font-weight="700">A</text>
  <text x="165" y="80" font-size="10" text-anchor="middle" font-family="'Fira Code',monospace" fill="#1a1f36d0" font-weight="700">B</text>
</svg>
</div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">A</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>}<br>
    <span style="color:#0e6ead;">B</span> = {<span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">5</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">A</span> | <span style="color:#0e6ead;">B</span>)<br>
    <span style="color:#6b7280;"># {1, 2, 3, 4, 5}</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-green" style="text-align:center;">
    <div class="slide-h2" style="color:var(--green);">Intersection  &amp;  A.intersection(B)</div>
    <div class="small-text" style="margin-top:4px;">Items present in both A and B.</div>
  </div>

  <div v-click class="venn-wrap">
<svg viewBox="0 0 220 130" width="220" height="130">
  <circle cx="80" cy="65" r="55" fill="none" stroke="#c73c3c" stroke-width="2"/>
  <circle cx="140" cy="65" r="55" fill="none" stroke="#2b6cb0" stroke-width="2"/>
  <path d="M 110 18 A 55 55 0 0 1 110 112 A 55 55 0 0 1 110 18 Z" fill="rgba(56,161,105,0.45)" stroke="#276749" stroke-width="2"/>
  <text x="55" y="80" font-size="10" text-anchor="middle" font-family="'Fira Code',monospace" fill="#1a1f36d0" font-weight="700">A</text>
  <text x="165" y="80" font-size="10" text-anchor="middle" font-family="'Fira Code',monospace" fill="#1a1f36d0" font-weight="700">B</text>
</svg>
</div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">A</span> = {<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">3</span>}<br>
    <span style="color:#0e6ead;">B</span> = {<span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>, <span style="color:#b45309;">5</span>}<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">A</span> &amp; <span style="color:#0e6ead;">B</span>)<br>
    <span style="color:#6b7280;"># {3}</span>
  </div>
</div>

</div>

  </template>
</Slide2>
