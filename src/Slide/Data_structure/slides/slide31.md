<Slide2 topic="Set Methods &amp; Practical Examples">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Set <span class="highlight">Methods</span> &amp; Examples</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="section-label">Quick Reference</div>

  <table v-after class="cmp-table">
    <thead>
      <tr><th>Method</th><th>Purpose</th></tr>
    </thead>
    <tbody>
      <tr><td class="mono">add(x)</td><td>Add one item</td></tr>
      <tr><td class="mono">update(iter)</td><td>Add many</td></tr>
      <tr><td class="mono">remove / discard</td><td>Delete an item</td></tr>
      <tr><td class="mono">pop / clear</td><td>Remove items</td></tr>
      <tr><td class="mono">union / |</td><td>Combine</td></tr>
      <tr><td class="mono">intersection / &amp;</td><td>Common items</td></tr>
      <tr><td class="mono">difference / -</td><td>Items only in A</td></tr>
      <tr><td class="mono">issubset / issuperset</td><td>Check inclusion</td></tr>
      <tr><td class="mono">copy()</td><td>Shallow copy</td></tr>
    </tbody>
  </table>
</div>

<div class="flex-col">
  <div v-click class="section-label">Example 1 — Remove Duplicates</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">names</span> = [<span style="color:#2d7a00;">"Anu"</span>, <span style="color:#2d7a00;">"Ravi"</span>, <span style="color:#2d7a00;">"Anu"</span>, <span style="color:#2d7a00;">"Sita"</span>]<br>
    <span style="color:#0e6ead;">uniq</span> = <span style="color:#2d7a00;">set</span>(<span style="color:#0e6ead;">names</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">uniq</span>)
  </div>

  <div v-click class="output-box">{'Anu', 'Ravi', 'Sita'}</div>

  <div v-click class="section-label" style="margin-top:6px;">Example 2 — Common Items</div>

  <div v-after class="code-block">
    <span style="color:#0e6ead;">A</span> = <span style="color:#2d7a00;">set</span>([<span style="color:#b45309;">1</span>,<span style="color:#b45309;">2</span>,<span style="color:#b45309;">3</span>,<span style="color:#b45309;">4</span>])<br>
    <span style="color:#0e6ead;">B</span> = <span style="color:#2d7a00;">set</span>([<span style="color:#b45309;">3</span>,<span style="color:#b45309;">4</span>,<span style="color:#b45309;">5</span>,<span style="color:#b45309;">6</span>])<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">A</span> &amp; <span style="color:#0e6ead;">B</span>)
  </div>

  <div v-click class="output-box">{3, 4}</div>
</div>

</div>

  </template>
</Slide2>
