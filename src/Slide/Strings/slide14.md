

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">String <span class="highlight">Formatting</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">String formatting</strong> lets you embed variable values inside a string cleanly. Python offers three approaches — <span class="mono">%</span>, <span class="mono">format()</span>, and <span class="mono">f-strings</span>.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Method 1 — % Formatting (Old Style)</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">name</span> = <span style="color:#2d7a00;">"Alice"</span>; <span style="color:#0e6ead;">age</span> = <span style="color:#b45309;">25</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Name: %s, Age: %d"</span> % (<span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>))<br>
    <span style="color:#6b7280;"># Name: Alice, Age: 25</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Pi = %.2f"</span> % <span style="color:#b45309;">3.14159</span>)<br>
    <span style="color:#6b7280;"># Pi = 3.14</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Method 2 — format() Method</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Name: {}, Age: {}"</span>.format(<span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">age</span>))<br>
    <span style="color:#6b7280;"># Name: Alice, Age: 25</span><br>
    <span style="color:#6b7280;"># With named placeholders</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Hello {name}, you are {age}!"</span>.format(name=<span style="color:#0e6ead;">name</span>, age=<span style="color:#0e6ead;">age</span>))<br>
    <span style="color:#6b7280;"># Hello Alice, you are 25!</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Method 3 — f-Strings (Recommended)</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Prefix string with f or F</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Name: <span style="color:#ef5050;">{name}</span>, Age: <span style="color:#ef5050;">{age}</span>"</span>)<br>
    <span style="color:#6b7280;"># Name: Alice, Age: 25</span><br><br>
    <span style="color:#6b7280;"># Expressions inside f-strings</span><br>
    <span style="color:#0e6ead;">price</span> = <span style="color:#b45309;">49.9</span><br>
    <span style="color:#0e6ead;">qty</span>   = <span style="color:#b45309;">3</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Total: ₹<span style="color:#ef5050;">{price * qty:.2f}</span>"</span>)<br>
    <span style="color:#6b7280;"># Total: ₹149.70</span><br><br>
    <span style="color:#6b7280;"># Padding and alignment</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"<span style="color:#ef5050;">{name:&gt;10}</span>"</span>)    <span style="color:#6b7280;"># "     Alice" (right align)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"<span style="color:#ef5050;">{age:05d}</span>"</span>)     <span style="color:#6b7280;"># "00025" (zero padded)</span>
  </div>

  <div v-click style="margin-top:8px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead><tr><th>Method</th><th>Python</th><th>Readability</th></tr></thead>
      <tbody>
        <tr><td class="mono">%</td><td>2.x+</td><td>Low</td></tr>
        <tr><td class="mono">format()</td><td>2.7+</td><td>Medium</td></tr>
        <tr><td class="mono" style="color:var(--green);font-weight:600;">f-string</td><td>3.6+</td><td class="yes">Best</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px; margin-bottom:40px">
    <div><strong>Use f-strings</strong> for all new Python 3 code — they're the fastest, most readable, and most powerful.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
