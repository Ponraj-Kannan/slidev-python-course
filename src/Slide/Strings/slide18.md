

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">String <span class="highlight">Comparison</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      Strings can be compared using the same <strong style="color:var(--red);">comparison operators</strong> as numbers. Python compares strings <strong>character by character</strong> using their <strong>Unicode (ASCII) values</strong>.
    </div>
  </div>

  <div  style="margin-top:6px;">
    <table class="cmp-table" style="font-size:.71rem;">
      <thead v-click><tr><th>Expression</th><th>Result</th><th>Why</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono">"abc" == "abc"</td><td class="yes">True</td><td>Identical characters</td></tr>
        <tr v-click><td class="mono">"abc" == "ABC"</td><td class="no">False</td><td>Case is different</td></tr>
        <tr v-click><td class="mono">"apple" &lt; "banana"</td><td class="yes">True</td><td>'a' (97) &lt; 'b' (98)</td></tr>
        <tr v-click><td class="mono">"cat" &gt; "car"</td><td class="yes">True</td><td>'t' (116) &gt; 'r' (114)</td></tr>
        <tr v-click><td class="mono">"z" &gt; "A"</td><td class="yes">True</td><td>'z' (122) &gt; 'A' (65)</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Python uses <strong>lexicographic order</strong> — the same order as a dictionary. Uppercase letters always have lower Unicode values than lowercase letters.</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Code Examples</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">a</span> = <span style="color:#2d7a00;">"hello"</span><br>
    <span style="color:#0e6ead;">b</span> = <span style="color:#2d7a00;">"Hello"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> == <span style="color:#0e6ead;">b</span>)            <span style="color:#6b7280;"># False (case-sensitive)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span>.lower() == <span style="color:#0e6ead;">b</span>.lower())  <span style="color:#6b7280;"># True (case-insensitive)</span><br><br>
    <span style="color:#6b7280;"># Alphabetical sorting check</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"apple"</span> < <span style="color:#2d7a00;">"mango"</span>)  <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"zebra"</span> > <span style="color:#2d7a00;">"ant"</span>)    <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Practical: Login Check</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">stored_pwd</span> = <span style="color:#2d7a00;">"Secure@123"</span><br>
    <span style="color:#0e6ead;">user_pwd</span>   = <span style="color:#ef5050;">input</span>(<span style="color:#2d7a00;">"Enter password: "</span>)<br>
    <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">user_pwd</span> == <span style="color:#0e6ead;">stored_pwd</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Access granted"</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Wrong password"</span>)</span>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px; margin-bottom:40px">
    <div><strong>Always compare after normalising:</strong> Use <span class="mono">.strip().lower()</span> on user input before comparing to avoid whitespace/case mismatches.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
