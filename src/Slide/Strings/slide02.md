<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Creating <span class="highlight">Strings</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      Python lets you create strings using <strong style="color:var(--red);">single quotes</strong>, <strong style="color:var(--red);">double quotes</strong>, or <strong style="color:var(--red);">triple quotes</strong>. All three are valid — choose based on your content.
    </div>
  </div>

  <div style="display:flex;flex-direction:column;gap:6px;margin-top:4px;">
    <div class="card-green" style="border-radius:8px;padding:10px 14px;" v-click >
      <div style="font-size:.72rem;font-weight:600;color:var(--green);margin-bottom:4px;font-family:'Fira Code',monospace;">Single Quotes &nbsp; ' '</div>
      <div style="font-size:.72rem;color:var(--slate);font-family:'Fira Code',monospace;">s = <span style="color:#2d7a00;">'Hello'</span></div>
    </div>
    <div class="card-blue" style="border-radius:8px;padding:10px 14px;" v-click >
      <div style="font-size:.72rem;font-weight:600;color:var(--blue);margin-bottom:4px;font-family:'Fira Code',monospace;">Double Quotes &nbsp; " "</div>
      <div style="font-size:.72rem;color:var(--slate);font-family:'Fira Code',monospace;">s = <span style="color:#2d7a00;">"Hello"</span></div>
    </div>
    <div class="card-orange" style="border-radius:8px;padding:10px 14px;" v-click >
      <div style="font-size:.72rem;font-weight:600;color:var(--orange);margin-bottom:4px;font-family:'Fira Code',monospace;">Triple Quotes &nbsp; ''' ''' &nbsp;or&nbsp; """ """</div>
      <div style="font-size:.72rem;color:var(--slate);font-family:'Fira Code',monospace;">s = <span style="color:#2d7a00;">"""Multi<br>&nbsp;&nbsp;&nbsp;&nbsp;line"""</span></div>
    </div>
  </div>

  <div v-click class="callout callout-danger" style="margin-top:4px;">
    <div><strong>Remember:</strong> Opening and closing quotes must <strong>match</strong>. <span class="mono">'Hello"</span> is a <span style="color:var(--red);font-weight:600;">SyntaxError</span>!</div>
  </div>

</div>

<div class="flex-col">
  <div v-click class="section-label">When to Use Which</div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Use double quotes when string has apostrophe</span><br>
    <span style="color:#0e6ead;">msg</span> = <span style="color:#2d7a00;">"It's a beautiful day"</span><br><br>
    <span style="color:#6b7280;"># Use single quotes when string has double quotes</span><br>
    <span style="color:#0e6ead;">quote</span> = <span style="color:#2d7a00;">'She said "hello"'</span><br><br>
    <span style="color:#6b7280;"># Triple quotes for multi-line text</span><br>
    <span style="color:#0e6ead;">poem</span> = <span style="color:#2d7a00;">"""Roses are red,</span><br>
    <span style="color:#2d7a00;">Violets are blue,</span><br>
    <span style="color:#2d7a00;">Python is awesome,</span><br>
    <span style="color:#2d7a00;">And so are you!"""</span><br><br>
    <span style="color:#6b7280;"># Using str() to convert other types</span><br>
    <span style="color:#0e6ead;">num_str</span> = <span style="color:#ef5050;">str</span>(<span style="color:#b45309;">42</span>)   <span style="color:#6b7280;"># "42"</span>
  </div>
</div>

</div>

  </template>
</Slide2>
