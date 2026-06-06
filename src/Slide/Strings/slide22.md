

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Real-World <span class="highlight">Examples</span> — Text Processing</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="section-label">Word Counter</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">text</span> = <span style="color:#2d7a00;">"Python is great. Python is fast!"</span><br>
    <span style="color:#0e6ead;">words</span> = <span style="color:#0e6ead;">text</span>.split()<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Words: <span style="color:#ef5050;">{len(words)}</span>"</span>)            <span style="color:#6b7280;"># Words: 6</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"'Python' appears: <span style="color:#ef5050;">{text.count('Python')}</span>"</span>)<br>
    <span style="color:#6b7280;"># 'Python' appears: 2</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Title Formatter</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># Clean and format a blog post title</span><br>
    <span style="color:#0e6ead;">raw</span> = <span style="color:#2d7a00;">"  the ART of python programming  "</span><br>
    <span style="color:#0e6ead;">title</span> = <span style="color:#0e6ead;">raw</span>.strip().title()<br>
    <span style="color:#0e6ead;">slug</span>  = <span style="color:#0e6ead;">title</span>.lower().replace(<span style="color:#2d7a00;">" "</span>, <span style="color:#2d7a00;">"-"</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">title</span>)  <span style="color:#6b7280;"># The Art Of Python Programming</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">slug</span>)   <span style="color:#6b7280;"># the-art-of-python-programming</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">CSV Row Parser</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">row</span>  = <span style="color:#2d7a00;">"Alice,25,Engineer,Chennai"</span><br>
    <span style="color:#0e6ead;">data</span> = <span style="color:#0e6ead;">row</span>.split(<span style="color:#2d7a00;">","</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Name: <span style="color:#ef5050;">{data[0]}</span>"</span>)    <span style="color:#6b7280;"># Alice</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Age:  <span style="color:#ef5050;">{data[1]}</span>"</span>)    <span style="color:#6b7280;"># 25</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Role: <span style="color:#ef5050;">{data[2]}</span>"</span>)    <span style="color:#6b7280;"># Engineer</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Receipt Generator</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">items</span>  = [(<span style="color:#2d7a00;">"Apple"</span>, <span style="color:#b45309;">3</span>, <span style="color:#b45309;">20</span>), (<span style="color:#2d7a00;">"Milk"</span>, <span style="color:#b45309;">2</span>, <span style="color:#b45309;">55</span>)]<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"="</span> * <span style="color:#b45309;">30</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"<span style="color:#ef5050;">{'RECEIPT':^30}</span>"</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"="</span> * <span style="color:#b45309;">30</span>)<br>
    <span style="color:#0e6ead;">total</span> = <span style="color:#b45309;">0</span><br>
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">name</span>, <span style="color:#0e6ead;">qty</span>, <span style="color:#0e6ead;">price</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">items</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">amt</span> = <span style="color:#0e6ead;">qty</span> * <span style="color:#0e6ead;">price</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"<span style="color:#ef5050;">{name:<15}</span>₹<span style="color:#ef5050;">{amt:>8}</span>"</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">total</span> += <span style="color:#0e6ead;">amt</span></span>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"-"</span> * <span style="color:#b45309;">30</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"<span style="color:#ef5050;">{'Total':<15}</span>₹<span style="color:#ef5050;">{total:>8}</span>"</span>)
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px; margin-bottom:40px">
    <div>f-string alignment: <span class="mono">&lt;</span> = left, <span class="mono">&gt;</span> = right, <span class="mono">^</span> = center. Combine with a width number: <span class="mono">f"{name:&lt;15}"</span> pads to 15 characters.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
