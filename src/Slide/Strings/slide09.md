<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Length <span class="highlight">&amp;</span> Membership</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">len()</strong> returns the total number of characters in a string, including spaces and punctuation. <strong style="color:var(--red);">in / not in</strong> check if a substring exists inside a string.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Using len()</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">len</span>(<span style="color:#2d7a00;">"Python"</span>))      <span style="color:#6b7280;"># 6</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">len</span>(<span style="color:#2d7a00;">"Hello World"</span>))  <span style="color:#6b7280;"># 11 (space counts!)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#ef5050;">len</span>(<span style="color:#2d7a00;">""</span>))            <span style="color:#6b7280;"># 0 (empty string)</span><br><br>
    <span style="color:#6b7280;"># Validate password length</span><br>
    <span style="color:#0e6ead;">pwd</span> = <span style="color:#2d7a00;">"Secure@123"</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">pwd</span>) >= <span style="color:#b45309;">8</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Strong password"</span>)</span>
    <span style="color:#6b7280;"># Strong password</span>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Note:</strong> <span class="mono">len()</span> counts characters, not words. For word count, use <span class="mono">len(s.split())</span>.</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Membership: in / not in</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">sentence</span> = <span style="color:#2d7a00;">"Python is fun to learn"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Python"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">sentence</span>)     <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Java"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">sentence</span>)       <span style="color:#6b7280;"># False</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Java"</span> <span style="color:#ef5050;">not in</span> <span style="color:#0e6ead;">sentence</span>)  <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"fun"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">sentence</span>)        <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Practical Use</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Spam word filter</span><br>
    <span style="color:#0e6ead;">message</span> = <span style="color:#2d7a00;">"Claim your free prize now!"</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#2d7a00;">"free"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">message</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Possible spam!"</span>)</span>
    <span style="color:#6b7280;"># Possible spam!</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px; margin-bottom:40px">
    <div>Membership checks are <strong>case-sensitive</strong>: <span class="mono">"python" in "Hello Python"</span> → <span class="mono" style="color:var(--red-dark);">False</span>. Use <span class="mono">.lower()</span> for case-insensitive search.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
