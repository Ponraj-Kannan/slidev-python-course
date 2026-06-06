

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">String</span> Cheatsheet</div>

<div class="g2" style="gap:12px;align-items:start;">

<div class="flex-col">

  <div v-click class="section-label">Indexing &amp; Slicing</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Python"</span><br>
    <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>]     <span style="color:#6b7280;"># 'P'   — first char</span><br>
    <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">-1</span>]    <span style="color:#6b7280;"># 'n'   — last char</span><br>
    <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">1</span>:<span style="color:#b45309;">4</span>]   <span style="color:#6b7280;"># 'yth' — slice</span><br>
    <span style="color:#0e6ead;">s</span>[::<span style="color:#b45309;">-1</span>]  <span style="color:#6b7280;"># 'nohtyP' — reverse</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Operators</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#2d7a00;">"Hi"</span> + <span style="color:#2d7a00;">" World"</span>      <span style="color:#6b7280;"># 'Hi World'</span><br>
    <span style="color:#2d7a00;">"ab"</span> * <span style="color:#b45309;">3</span>          <span style="color:#6b7280;"># 'ababab'</span><br>
    <span style="color:#ef5050;">len</span>(<span style="color:#2d7a00;">"hello"</span>)        <span style="color:#6b7280;"># 5</span><br>
    <span style="color:#2d7a00;">"hi"</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">"hi there"</span>  <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Formatting</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#0e6ead;">n</span>, <span style="color:#0e6ead;">x</span> = <span style="color:#2d7a00;">"Alice"</span>, <span style="color:#b45309;">3.14</span><br>
    <span style="color:#2d7a00;">f"Hello <span style="color:#ef5050;">{n}</span>, pi=<span style="color:#ef5050;">{x:.2f}</span>"</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Key Methods Quick Reference</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.69rem;line-height:1.85;">
    <span style="color:#2d7a00;">"hi"</span>.upper()            <span style="color:#6b7280;"># 'HI'</span><br>
    <span style="color:#2d7a00;">"HI"</span>.lower()            <span style="color:#6b7280;"># 'hi'</span><br>
    <span style="color:#2d7a00;">"hi there"</span>.title()     <span style="color:#6b7280;"># 'Hi There'</span><br>
    <span style="color:#2d7a00;">"  hi  "</span>.strip()       <span style="color:#6b7280;"># 'hi'</span><br>
    <span style="color:#2d7a00;">"a-b-c"</span>.split(<span style="color:#2d7a00;">"-"</span>)    <span style="color:#6b7280;"># ['a','b','c']</span><br>
    <span style="color:#2d7a00;">"-"</span>.join([<span style="color:#2d7a00;">"a"</span>,<span style="color:#2d7a00;">"b"</span>])   <span style="color:#6b7280;"># 'a-b'</span><br>
    <span style="color:#2d7a00;">"abc"</span>.replace(<span style="color:#2d7a00;">"a"</span>,<span style="color:#2d7a00;">"x"</span>) <span style="color:#6b7280;"># 'xbc'</span><br>
    <span style="color:#2d7a00;">"abcabc"</span>.find(<span style="color:#2d7a00;">"b"</span>)     <span style="color:#6b7280;"># 1</span><br>
    <span style="color:#2d7a00;">"abab"</span>.count(<span style="color:#2d7a00;">"ab"</span>)     <span style="color:#6b7280;"># 2</span><br>
    <span style="color:#2d7a00;">"hi.py"</span>.endswith(<span style="color:#2d7a00;">".py"</span>)<span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Iteration</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:10px 14px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">"abc"</span>: <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">ch</span>)<br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span>, <span style="color:#0e6ead;">ch</span> <span style="color:#ef5050;">in</span> <span style="color:#ef5050;">enumerate</span>(<span style="color:#2d7a00;">"abc"</span>): ...
  </div>

  <div v-click class="callout callout-info" style="margin-top:8px; margin-bottom:40px">
    <div>Bookmark this slide! These are the most-used string operations you will encounter in every Python project.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
