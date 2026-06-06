

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Common <span class="highlight">Mistakes</span> to Avoid</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-red" style="border-radius:10px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--red-dark);margin-bottom:4px;">Mistake 1 — Using + to mix str and int</div>
    <div style="background:#fff8f8;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#6b7280;"># Wrong — TypeError!</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Age: "</span> + <span style="color:#b45309;">25</span>)<br><br>
      <span style="color:#6b7280;"># Correct</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Age: "</span> + <span style="color:#ef5050;">str</span>(<span style="color:#b45309;">25</span>))<br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Age: <span style="color:#ef5050;">{25}</span>"</span>)  <span style="color:#6b7280;"># Best way</span>
    </div>
  </div>

  <div v-click class="card-red" style="border-radius:10px;margin-top:8px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--red-dark);margin-bottom:4px;">Mistake 2 — Trying to Modify a String</div>
    <div style="background:#fff8f8;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"hello"</span><br>
      <span style="color:#6b7280;"># Wrong — TypeError!</span><br>
      <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>] = <span style="color:#2d7a00;">"H"</span><br><br>
      <span style="color:#6b7280;"># Correct — create a new string</span><br>
      <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"H"</span> + <span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">1</span>:]  <span style="color:#6b7280;"># "Hello"</span>
    </div>
  </div>

  <div v-click class="card-red" style="border-radius:10px;margin-top:8px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--red-dark);margin-bottom:4px;">Mistake 3 — Index Out of Range</div>
    <div style="background:#fff8f8;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"abc"</span>  <span style="color:#6b7280;"># length 3</span><br>
      <span style="color:#6b7280;"># Wrong — IndexError!</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">5</span>])<br><br>
      <span style="color:#6b7280;"># Correct — check length first</span><br>
      <span style="color:#ef5050;">if</span> <span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">s</span>) > <span style="color:#b45309;">5</span>: <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">5</span>])
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="card-red" style="border-radius:10px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--red-dark);margin-bottom:4px;">Mistake 4 — Forgetting Case Sensitivity</div>
    <div style="background:#fff8f8;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">name</span> = <span style="color:#2d7a00;">"Alice"</span><br>
      <span style="color:#6b7280;"># Wrong — False! "alice" ≠ "Alice"</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span> == <span style="color:#2d7a00;">"alice"</span>)<br><br>
      <span style="color:#6b7280;"># Correct — normalise before comparing</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">name</span>.lower() == <span style="color:#2d7a00;">"alice"</span>)  <span style="color:#6b7280;"># True</span>
    </div>
  </div>

  <div v-click class="card-red" style="border-radius:10px;margin-top:8px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--red-dark);margin-bottom:4px;">Mistake 5 — Forgetting Methods Return New Strings</div>
    <div style="background:#fff8f8;border-radius:8px;padding:10px 12px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"hello"</span><br>
      <span style="color:#6b7280;"># Wrong — s is still "hello"!</span><br>
      <span style="color:#0e6ead;">s</span>.upper()<br><br>
      <span style="color:#6b7280;"># Correct — capture the result</span><br>
      <span style="color:#0e6ead;">s</span> = <span style="color:#0e6ead;">s</span>.upper()  <span style="color:#6b7280;"># Now s = "HELLO"</span>
    </div>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:8px; margin-bottom:40px">
    <div><strong>Golden Rule:</strong> Always <strong>assign the result</strong> of a string method back to a variable — strings are immutable, so methods never change the original.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
