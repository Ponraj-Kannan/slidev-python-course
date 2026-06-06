

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Escape <span class="highlight">Characters</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Escape characters</strong> are special sequences starting with a backslash <span class="mono">\</span> that represent characters which are otherwise hard or impossible to type directly inside a string.
    </div>
  </div>

  <div style="margin-top:6px;">
    <table class="cmp-table" style="font-size:.71rem;">
      <thead v-click><tr><th>Escape</th><th>Meaning</th><th>Output</th></tr></thead>
      <tbody>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">\n</td><td>Newline</td><td>Moves to next line</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">\t</td><td>Tab</td><td>Horizontal tab space</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">\\</td><td>Backslash</td><td>\</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">\'</td><td>Single quote</td><td>'</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">\"</td><td>Double quote</td><td>"</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">\r</td><td>Carriage return</td><td>Cursor to start of line</td></tr>
        <tr v-click><td class="mono" style="color:var(--red-dark);font-weight:600;">\0</td><td>Null character</td><td>Empty byte</td></tr>
      </tbody>
    </table>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Code Examples</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Newline and tab</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Line 1\nLine 2"</span>)<br>
    <span style="color:#6b7280;"># Line 1</span><br>
    <span style="color:#6b7280;"># Line 2</span><br><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Name:\tAlice"</span>)  <span style="color:#6b7280;"># Name:   Alice</span><br><br>
    <span style="color:#6b7280;"># Quotes inside strings</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"She said \"Hello\""</span>)<br>
    <span style="color:#6b7280;"># She said "Hello"</span><br><br>
    <span style="color:#6b7280;"># File path (backslash)</span><br>
    <span style="color:#0e6ead;">path</span> = <span style="color:#2d7a00;">"C:\\Users\\Alice\\file.txt"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">path</span>)<br>
    <span style="color:#6b7280;"># C:\Users\Alice\file.txt</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Raw Strings — Ignore Escape</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Prefix r or R to ignore escape sequences</span><br>
    <span style="color:#0e6ead;">path</span> = <span style="color:#2d7a00;">r"C:\Users\Alice\file.txt"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">path</span>)  <span style="color:#6b7280;"># C:\Users\Alice\file.txt</span>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px; margin-bottom:40px">
    <div>Use <strong>raw strings</strong> (<span class="mono">r"..."</span>) for Windows file paths and <strong>regex patterns</strong> to avoid unintended escape interpretation.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
