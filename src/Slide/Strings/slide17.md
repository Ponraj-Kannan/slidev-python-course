---
transition: slide-up
---

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Multiline <span class="highlight">Strings</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Multiline strings</strong> span across multiple lines. Use <strong>triple quotes</strong> (<span class="mono">"""</span> or <span class="mono">'''</span>) to write text across several lines without needing <span class="mono">\n</span> everywhere.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Triple Double Quotes</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">address</span> = <span style="color:#2d7a00;">"""123 Main Street,</span><br>
    <span style="color:#2d7a00;">Chennai,</span><br>
    <span style="color:#2d7a00;">Tamil Nadu — 600001"""</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">address</span>)<br>
    <span style="color:#6b7280;"># 123 Main Street,</span><br>
    <span style="color:#6b7280;"># Chennai,</span><br>
    <span style="color:#6b7280;"># Tamil Nadu — 600001</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Triple Single Quotes</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">poem</span> = <span style="color:#2d7a00;">'''Roses are red,</span><br>
    <span style="color:#2d7a00;">Violets are blue,</span><br>
    <span style="color:#2d7a00;">Python is amazing,</span><br>
    <span style="color:#2d7a00;">And so are you!'''</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">poem</span>)
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Multiline as Docstrings</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">def</span> <span style="color:#0e6ead;">greet</span>(<span style="color:#0e6ead;">name</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"""</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">Greet a person by name.</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">Args: name (str) — person's name</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">"""</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">return</span> <span style="color:#2d7a00;">f"Hello, <span style="color:#ef5050;">{name}</span>!"</span></span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Multiline vs \n</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Both produce the same output</span><br>
    <span style="color:#0e6ead;">s1</span> = <span style="color:#2d7a00;">"Line 1\nLine 2\nLine 3"</span><br>
    <span style="color:#0e6ead;">s2</span> = <span style="color:#2d7a00;">"""Line 1</span><br>
    <span style="color:#2d7a00;">Line 2</span><br>
    <span style="color:#2d7a00;">Line 3"""</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s1</span> == <span style="color:#0e6ead;">s2</span>)  <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div><strong>Watch out:</strong> Indentation inside triple quotes <strong>is part of the string</strong>. Leading spaces on each line will appear in the output.</div>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> HTML templates, SQL queries, email bodies, docstrings, configuration blocks</div>
  </div>

</div>

</div>

  </template>
</Slide2>
