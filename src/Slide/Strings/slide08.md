<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Concatenation <span class="highlight">&amp;</span> Repetition</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy">
    <div style="font-size:.8rem;line-height:1.6;color:var(--slate);">
      <strong style="color:var(--red);">Concatenation</strong> joins two or more strings using the <span class="mono">+</span> operator. <strong style="color:var(--red);">Repetition</strong> repeats a string using the <span class="mono">*</span> operator.
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">String Concatenation ( + )</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">first</span> = <span style="color:#2d7a00;">"Hello"</span><br>
    <span style="color:#0e6ead;">last</span>  = <span style="color:#2d7a00;">"World"</span><br>
    <span style="color:#0e6ead;">result</span> = <span style="color:#0e6ead;">first</span> + <span style="color:#2d7a00;">", "</span> + <span style="color:#0e6ead;">last</span> + <span style="color:#2d7a00;">"!"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">result</span>)  <span style="color:#6b7280;"># Hello, World!</span><br><br>
    <span style="color:#6b7280;"># Building a full name</span><br>
    <span style="color:#0e6ead;">fname</span> = <span style="color:#2d7a00;">"Ada"</span><br>
    <span style="color:#0e6ead;">lname</span> = <span style="color:#2d7a00;">"Lovelace"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">fname</span> + <span style="color:#2d7a00;">" "</span> + <span style="color:#0e6ead;">lname</span>)  <span style="color:#6b7280;"># Ada Lovelace</span>
  </div>

  <div v-click class="callout callout-danger">
    <div><strong>TypeError:</strong> You cannot use <span class="mono">+</span> to join a string and a number directly. Use <span class="mono">str(42)</span> to convert first.</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">String Repetition ( * )</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Ha"</span> * <span style="color:#b45309;">3</span>)      <span style="color:#6b7280;"># HaHaHa</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"-"</span> * <span style="color:#b45309;">20</span>)     <span style="color:#6b7280;"># -------------------- (divider)</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"abc"</span> * <span style="color:#b45309;">0</span>)    <span style="color:#6b7280;"># "" (empty string)</span><br><br>
    <span style="color:#6b7280;"># Practical use: progress bar</span><br>
    <span style="color:#0e6ead;">progress</span> = <span style="color:#b45309;">7</span><br>
    <span style="color:#0e6ead;">bar</span> = <span style="color:#2d7a00;">"#"</span> * <span style="color:#0e6ead;">progress</span> + <span style="color:#2d7a00;">"."</span> * (<span style="color:#b45309;">10</span> - <span style="color:#0e6ead;">progress</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"["</span> + <span style="color:#0e6ead;">bar</span> + <span style="color:#2d7a00;">"]"</span>)  <span style="color:#6b7280;"># [#######...]</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Augmented Concatenation ( += )</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">sentence</span> = <span style="color:#2d7a00;">"Python"</span><br>
    <span style="color:#0e6ead;">sentence</span> += <span style="color:#2d7a00;">" is"</span><br>
    <span style="color:#0e6ead;">sentence</span> += <span style="color:#2d7a00;">" awesome!"</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">sentence</span>)  <span style="color:#6b7280;"># Python is awesome!</span>
  </div>

  <div v-click class="card card-blue" style="margin-top:6px; margin-bottom:40px">
    <div class="small-text"><strong>Real-world use:</strong> Building greetings, formatting reports, creating separators, composing messages dynamically</div>
  </div>

</div>

</div>

  </template>
</Slide2>
