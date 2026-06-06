<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">String <span class="highlight">Methods</span> — Case &amp; Whitespace</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      String <strong style="color:var(--red);">methods</strong> are built-in functions that operate on strings. They are called using <span class="mono">string.method()</span>. Since strings are <strong>immutable</strong>, methods always return a <strong>new string</strong>.
    </div>
  </div>

  <div style="margin-top:6px;">
    <table class="cmp-table" style="font-size:.7rem;">
      <thead v-click><tr><th>Method</th><th>Description</th><th>Example → Output</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">upper()</td><td>All UPPERCASE</td><td class="mono">"hello".upper() → "HELLO"</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">lower()</td><td>All lowercase</td><td class="mono">"HELLO".lower() → "hello"</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">title()</td><td>Title Case Words</td><td class="mono">"hello world".title() → "Hello World"</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">capitalize()</td><td>First letter only</td><td class="mono">"hello world".capitalize() → "Hello world"</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">strip()</td><td>Remove leading/trailing spaces</td><td class="mono">"  hi  ".strip() → "hi"</td></tr>
      </tbody>
    </table>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Code Examples</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"  hello, world!  "</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.upper())        <span style="color:#6b7280;"># "  HELLO, WORLD!  "</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.lower())        <span style="color:#6b7280;"># "  hello, world!  "</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.title())        <span style="color:#6b7280;"># "  Hello, World!  "</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.capitalize())   <span style="color:#6b7280;"># "  hello, world!  " → only 1st non-space</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.strip())        <span style="color:#6b7280;"># "hello, world!"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.lstrip())       <span style="color:#6b7280;"># "hello, world!  " (left only)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>.rstrip())       <span style="color:#6b7280;"># "  hello, world!" (right only)</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Chaining Methods</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Clean user input: strip spaces + lowercase</span><br>
    <span style="color:#0e6ead;">user_input</span> = <span style="color:#2d7a00;">"  ALICE  "</span><br>
    <span style="color:#0e6ead;">clean</span> = <span style="color:#0e6ead;">user_input</span>.strip().lower()<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">clean</span>)  <span style="color:#6b7280;"># alice</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px; margin-bottom:40px">
    <div><strong>Real-world:</strong> Use <span class="mono">.strip().lower()</span> when comparing user input to avoid mismatches from accidental spaces or caps.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
