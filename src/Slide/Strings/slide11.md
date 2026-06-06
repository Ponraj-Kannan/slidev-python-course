<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">String Methods — <span class="highlight">Search &amp; Replace</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      These methods let you <strong style="color:var(--red);">search</strong> for substrings and <strong style="color:var(--red);">replace</strong> or <strong style="color:var(--red);">count</strong> their occurrences within a string.
    </div>
  </div>

  <div style="margin-top:6px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Method</th><th>What It Does</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">replace(old, new)</td><td>Replaces all occurrences of <em>old</em> with <em>new</em></td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">find(sub)</td><td>Returns index of first match, or <span class="mono">-1</span> if not found</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">count(sub)</td><td>Counts how many times <em>sub</em> appears</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">startswith(prefix)</td><td>Returns <span class="mono yes">True</span> if string starts with <em>prefix</em></td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">endswith(suffix)</td><td>Returns <span class="mono yes">True</span> if string ends with <em>suffix</em></td></tr>
      </tbody>
    </table>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Code Examples</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"banana is a tasty banana"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.replace(<span style="color:#2d7a00;">"banana"</span>, <span style="color:#2d7a00;">"mango"</span>))<br>
    <span style="color:#6b7280;"># mango is a tasty mango</span><br><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.find(<span style="color:#2d7a00;">"tasty"</span>))  <span style="color:#6b7280;"># 13</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.find(<span style="color:#2d7a00;">"grape"</span>))  <span style="color:#6b7280;"># -1 (not found)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.count(<span style="color:#2d7a00;">"banana"</span>)) <span style="color:#6b7280;"># 2</span>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:6px;">
    <span style="color:#6b7280;"># File type detection</span><br>
    <span style="color:#0e6ead;">filename</span> = <span style="color:#2d7a00;">"report.pdf"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">filename</span>.endswith(<span style="color:#2d7a00;">".pdf"</span>))   <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">filename</span>.startswith(<span style="color:#2d7a00;">"rep"</span>))  <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div><strong>find() vs index():</strong> <span class="mono">find()</span> returns <span class="mono">-1</span> if not found. <span class="mono">index()</span> raises a <strong>ValueError</strong>. Prefer <span class="mono">find()</span> when unsure.</div>
  </div>

  <div v-click class="card card-green" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> Censoring words, detecting file types, validating email domains, search-and-replace in documents</div>
  </div>

</div>

</div>

  </template>
</Slide2>
