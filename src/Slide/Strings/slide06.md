<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">String <span class="highlight">Slicing</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Slicing</strong> extracts a <strong>substring</strong> (a portion of a string) using the syntax <span class="mono">s[start:stop:step]</span>.
    </div>
  </div>

  <div v-click style="margin-top:6px;">
    <div class="section-label" style="margin-bottom:6px;">Syntax Breakdown</div>
    <div class="syntax-row" style="justify-content:center;">
      <div style="text-align:center;">
        <div class="syn-varname">start</div>
        <div class="syn-label">Begin index (inclusive)</div>
      </div>
      <div class="step-arrow">:</div>
      <div style="text-align:center;">
        <div class="syn-keyword">stop</div>
        <div class="syn-label">End index (exclusive)</div>
      </div>
      <div class="step-arrow">:</div>
      <div style="text-align:center;">
        <div class="syn-value">step</div>
        <div class="syn-label">Jump amount (optional)</div>
      </div>
    </div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;margin-top:8px;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Hello, World!"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>:<span style="color:#b45309;">5</span>])   <span style="color:#6b7280;"># Hello</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">7</span>:<span style="color:#b45309;">12</span>])  <span style="color:#6b7280;"># World</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[:<span style="color:#b45309;">5</span>])    <span style="color:#6b7280;"># Hello (start defaults to 0)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">7</span>:])    <span style="color:#6b7280;"># World! (stop defaults to end)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[:])     <span style="color:#6b7280;"># Hello, World! (full copy)</span>
  </div>

  <div v-click class="callout callout-info">
    <div>The <strong>stop index is exclusive</strong> — <span class="mono">s[0:5]</span> gives characters at positions 0, 1, 2, 3, 4 (not 5).</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Step / Stride Slicing</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"abcdefgh"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>:<span style="color:#b45309;">8</span>:<span style="color:#b45309;">2</span>])  <span style="color:#6b7280;"># aceg (every 2nd character)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[::<span style="color:#b45309;">2</span>])     <span style="color:#6b7280;"># aceg</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[::<span style="color:#b45309;">-1</span>])    <span style="color:#6b7280;"># hgfedcba (reverse!)</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Practical Slicing Tricks</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">email</span> = <span style="color:#2d7a00;">"user@example.com"</span><br>
    <span style="color:#6b7280;"># Extract username (before @)</span><br>
    <span style="color:#0e6ead;">at</span> = <span style="color:#0e6ead;">email</span>.find(<span style="color:#2d7a00;">"@"</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">email</span>[:<span style="color:#0e6ead;">at</span>])    <span style="color:#6b7280;"># user</span><br><br>
    <span style="color:#6b7280;"># Reverse a string</span><br>
    <span style="color:#0e6ead;">word</span> = <span style="color:#2d7a00;">"racecar"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">word</span>[::<span style="color:#b45309;">-1</span>])  <span style="color:#6b7280;"># racecar (palindrome!)</span>
  </div>

  <div v-click class="card card-orange" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> Extracting file extensions, parsing dates, reversing strings, skipping characters</div>
  </div>

</div>

</div>

  </template>
</Slide2>
