<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Accessing <span class="highlight">Characters</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      Use <strong style="color:var(--red);">square brackets [ ]</strong> with an index to access any single character. Positive indices count from the <strong>left</strong>, negative from the <strong>right</strong>.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Positive Indexing</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Python"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>])  <span style="color:#6b7280;"># P  ← first character</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">1</span>])  <span style="color:#6b7280;"># y</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">3</span>])  <span style="color:#6b7280;"># h</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">5</span>])  <span style="color:#6b7280;"># n  ← last character</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Negative Indexing</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Python"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">-1</span>]) <span style="color:#6b7280;"># n  ← last character</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">-2</span>]) <span style="color:#6b7280;"># o</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">-6</span>]) <span style="color:#6b7280;"># P  ← first character</span>
  </div>

  <div v-click class="callout callout-danger">
    <div><strong>IndexError:</strong> <span class="mono">s[10]</span> on a 6-character string crashes! Always keep index within range.</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Index Map: "Python"</div>
  <div v-after style="background:#f7f8fc;border-radius:10px;border:1px solid var(--border);padding:14px;">
    <table class="trace-table">
      <thead>
        <tr><th>Character</th><th>P</th><th>y</th><th>t</th><th>h</th><th>o</th><th>n</th></tr>
      </thead>
      <tbody>
        <tr><td style="font-weight:600;color:var(--blue);">+ve index</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr>
        <tr><td style="font-weight:600;color:var(--red-dark);">-ve index</td><td>-6</td><td>-5</td><td>-4</td><td>-3</td><td>-2</td><td>-1</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Real-World Example</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Get first and last character of username</span><br>
    <span style="color:#0e6ead;">username</span> = <span style="color:#2d7a00;">"alice2024"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"First:"</span>, <span style="color:#0e6ead;">username</span>[<span style="color:#b45309;">0</span>])   <span style="color:#6b7280;"># a</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Last:"</span>, <span style="color:#0e6ead;">username</span>[<span style="color:#b45309;">-1</span>])   <span style="color:#6b7280;"># 4</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px; margin-bottom:40px">
    <div><strong>Tip:</strong> Use <span class="mono">s[-1]</span> instead of <span class="mono">s[len(s)-1]</span> to always get the last character — it's cleaner and Pythonic!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
