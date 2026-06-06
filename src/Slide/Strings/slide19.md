

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Iterating Through <span class="highlight">Strings</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      Because strings are <strong style="color:var(--red);">ordered sequences</strong>, you can loop through every character using a <span class="mono">for</span> loop or access them by index with a <span class="mono">while</span> loop.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">for Loop — Character by Character</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Python"</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">s</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">ch</span>, end=<span style="color:#2d7a00;">" "</span>)</span>
    <span style="color:#6b7280;"># P y t h o n</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">for Loop with enumerate()</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span>, <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#ef5050;">enumerate</span>(<span style="color:#2d7a00;">"hi!"</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"[<span style="color:#ef5050;">{i}</span>] = <span style="color:#ef5050;">{ch}</span>"</span>)</span>
    <span style="color:#6b7280;"># [0] = h</span><br>
    <span style="color:#6b7280;"># [1] = i</span><br>
    <span style="color:#6b7280;"># [2] = !</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">while Loop — Index-Based</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"abc"</span>; <span style="color:#0e6ead;">i</span> = <span style="color:#b45309;">0</span><br>
    <span style="color:#ef5050;">while</span> <span style="color:#0e6ead;">i</span> < <span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">s</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#0e6ead;">i</span>])</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">i</span> += <span style="color:#b45309;">1</span></span>
    <span style="color:#6b7280;"># a  b  c</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Practical: Count Vowels</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">sentence</span> = <span style="color:#2d7a00;">"Hello Python World"</span><br>
    <span style="color:#0e6ead;">vowels</span>   = <span style="color:#2d7a00;">"aeiouAEIOU"</span><br>
    <span style="color:#0e6ead;">count</span>    = <span style="color:#b45309;">0</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">sentence</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">vowels</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#0e6ead;">count</span> += <span style="color:#b45309;">1</span></span>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Vowels: <span style="color:#ef5050;">{count}</span>"</span>)  <span style="color:#6b7280;"># Vowels: 5</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Practical: Reverse Using Loop</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Python"</span>; <span style="color:#0e6ead;">rev</span> = <span style="color:#2d7a00;">""</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">s</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">rev</span> = <span style="color:#0e6ead;">ch</span> + <span style="color:#0e6ead;">rev</span></span>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">rev</span>)  <span style="color:#6b7280;"># nohtyP</span>
  </div>

  <div v-click class="card card-orange" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> Text analysis, counting characters, parsing tokens, building output strings character by character</div>
  </div>

</div>

</div>

  </template>
</Slide2>
