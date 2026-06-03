<Slide2 topic="Common Mistakes — Sets &amp; Dictionaries">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Common Mistakes — <span class="highlight">Sets</span> &amp; <span class="highlight">Dicts</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-green">
    <div class="slide-h3" style="color:var(--green);">Set: Expecting Order</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">s</span> = {<span style="color:#b45309;">3</span>, <span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>}<br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>)  <span style="color:#6b7280;"># order is undefined</span><br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">s</span>[<span style="color:#b45309;">0</span>])  <span style="color:#c0392b;font-weight:700;"># TypeError</span>
    </div>
    <div class="small-text" style="margin-top:4px;"><strong>Fix:</strong> Convert to list and sort if order needed: <span class="mono">sorted(s)</span>.</div>
  </div>

  <div v-click class="card card-green">
    <div class="slide-h3" style="color:var(--green);">Set: Wrong Empty Syntax</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">s</span> = {}            <span style="color:#6b7280;"># dict, not set!</span><br>
      <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">set</span>()         <span style="color:#6b7280;"># correct</span>
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-blue">
    <div class="slide-h3" style="color:var(--blue);">Dict: Missing Key</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">d</span> = {<span style="color:#2d7a00;">"a"</span>: <span style="color:#b45309;">1</span>}<br>
      <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">d</span>[<span style="color:#2d7a00;">"b"</span>])<br>
      <span style="color:#c0392b;font-weight:700;"># KeyError</span>
    </div>
    <div class="small-text" style="margin-top:4px;"><strong>Fix:</strong> Use <span class="mono">d.get("b", default)</span> or <span class="mono">"b" in d</span>.</div>
  </div>

  <div v-click class="card card-blue">
    <div class="slide-h3" style="color:var(--blue);">Dict: Unhashable Key</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">d</span> = {[<span style="color:#b45309;">1</span>,<span style="color:#b45309;">2</span>]: <span style="color:#2d7a00;">"oops"</span>}<br>
      <span style="color:#c0392b;font-weight:700;"># TypeError: unhashable</span>
    </div>
    <div class="small-text" style="margin-top:4px;"><strong>Fix:</strong> Use immutable keys — strings, numbers, tuples.</div>
  </div>
</div>

</div>

<div v-click class="callout callout-success" style="margin-top:10px;font-size:.7rem;">
  <div><strong>Best practice:</strong> Defensive code — check or use safe accessors before reading data you didn't write.</div>
</div>

  </template>
</Slide2>
