

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Summary</span> — Core Concepts</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="section-label">Creating &amp; Characteristics</div>
  <div v-after style="display:flex;flex-direction:column;gap:6px;">
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-red" style="font-size:.85rem;">1</div>
      <div style="font-size:.73rem;color:var(--slate);">Created with <span class="mono">'...'</span>, <span class="mono">"..."</span>, or <span class="mono">"""..."""</span></div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-red" style="font-size:.85rem;">2</div>
      <div style="font-size:.73rem;color:var(--slate);">Strings are <strong>immutable</strong> and <strong>ordered sequences</strong></div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-red" style="font-size:.85rem;">3</div>
      <div style="font-size:.73rem;color:var(--slate);">Every character has a <strong>positive</strong> and <strong>negative</strong> index</div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Access, Slice &amp; Combine</div>
  <div v-after style="display:flex;flex-direction:column;gap:6px;">
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-blue" style="font-size:.85rem;">4</div>
      <div style="font-size:.73rem;color:var(--slate);"><span class="mono">s[i]</span> accesses one character; <span class="mono">s[start:stop:step]</span> slices</div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-blue" style="font-size:.85rem;">5</div>
      <div style="font-size:.73rem;color:var(--slate);"><span class="mono">+</span> concatenates; <span class="mono">*</span> repeats; <span class="mono">len()</span> gives length</div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-blue" style="font-size:.85rem;">6</div>
      <div style="font-size:.73rem;color:var(--slate);"><span class="mono">in</span> / <span class="mono">not in</span> check for substrings — return <span class="mono">True</span> or <span class="mono">False</span></div>
    </div>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Escape &amp; Multiline</div>
  <div v-after style="display:flex;flex-direction:column;gap:6px;">
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-orange" style="font-size:.85rem;">7</div>
      <div style="font-size:.73rem;color:var(--slate);"><span class="mono">\n</span> <span class="mono">\t</span> <span class="mono">\\</span> <span class="mono">\"</span> are escape sequences inside strings</div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-orange" style="font-size:.85rem;">8</div>
      <div style="font-size:.73rem;color:var(--slate);">Triple quotes allow multiline strings and docstrings</div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:center;">
      <div class="icon-circle ic-orange" style="font-size:.85rem;">9</div>
      <div style="font-size:.73rem;color:var(--slate);"><span class="mono">r"..."</span> raw strings ignore escape sequences</div>
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Methods at a Glance</div>
  <div v-after style="margin-top:4px;">
    <table class="cmp-table" style="font-size:.68rem;">
      <thead><tr><th>Category</th><th>Methods</th></tr></thead>
      <tbody>
        <tr v-click><td style="font-weight:600;color:var(--blue);">Case</td><td class="mono">upper()  lower()  title()  capitalize()</td></tr>
        <tr v-click><td style="font-weight:600;color:var(--green);">Whitespace</td><td class="mono">strip()  lstrip()  rstrip()</td></tr>
        <tr v-click><td style="font-weight:600;color:var(--orange);">Search</td><td class="mono">find()  count()  startswith()  endswith()</td></tr>
        <tr v-click><td style="font-weight:600;color:var(--red-dark);">Modify</td><td class="mono">replace()</td></tr>
        <tr v-click><td style="font-weight:600;color:var(--navy-mid);">Split/Join</td><td class="mono">split()  join()</td></tr>
      </tbody>
    </table>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Formatting</div>
  <div v-after style="display:flex;gap:8px;flex-wrap:wrap;margin-top:4px;">
    <div class="card-navy" style="border-radius:8px;padding:8px 12px;font-size:.7rem;flex:1;">
      <div class="mono" style="font-weight:600;color:var(--red-dark);margin-bottom:2px;">% formatting</div>
      <div style="color:var(--slate);">Legacy style — avoid in new code</div>
    </div>
    <div class="card-navy" style="border-radius:8px;padding:8px 12px;font-size:.7rem;flex:1;">
      <div class="mono" style="font-weight:600;color:var(--blue);margin-bottom:2px;">format()</div>
      <div style="color:var(--slate);">More readable than %</div>
    </div>
    <div class="card-green" style="border-radius:8px;padding:8px 12px;font-size:.7rem;flex:1;">
      <div class="mono" style="font-weight:600;color:var(--green);margin-bottom:2px;">f-strings</div>
      <div style="color:var(--slate);">Recommended — fastest and clearest</div>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:8px; margin-bottom:40px">
    <div><strong>Remember:</strong> Strings are immutable. All methods <strong>return a new string</strong> — always capture the result with an assignment.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
