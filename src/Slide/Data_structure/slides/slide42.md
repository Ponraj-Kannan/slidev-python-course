<Slide2 topic="Real-World Use Cases — Part 1">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Real-World Use Cases — <span class="highlight">Part 1</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-red">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-red">List</span>
      <div class="slide-h3" style="color:var(--red-dark);">Student Marks Management</div>
    </div>
    <div class="body-text" style="margin-top:4px;">An ordered series of marks, mutable as new exam results come in.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">marks</span> = [<span style="color:#b45309;">82</span>, <span style="color:#b45309;">76</span>, <span style="color:#b45309;">91</span>]
    </div>
  </div>

  <div v-click class="card card-blue">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-blue">Dict</span>
      <div class="slide-h3" style="color:var(--blue);">Employee Database</div>
    </div>
    <div class="body-text" style="margin-top:4px;">Each employee ID maps to a record (name, dept, salary).</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">emp</span> = {<span style="color:#2d7a00;">"E01"</span>: {<span style="color:#2d7a00;">"name"</span>:<span style="color:#2d7a00;">"Anu"</span>}}
    </div>
  </div>

  <div v-click class="card card-red">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-red">List</span>
      <div class="slide-h3" style="color:var(--red-dark);">Shopping Cart</div>
    </div>
    <div class="body-text" style="margin-top:4px;">Items appear in the order they were added; can be removed.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">cart</span>.<span style="color:#0e6ead;">append</span>(<span style="color:#2d7a00;">"Milk"</span>)
    </div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-blue">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-blue">Dict</span>
      <div class="slide-h3" style="color:var(--blue);">Contact Book</div>
    </div>
    <div class="body-text" style="margin-top:4px;">Name -> phone number — instant lookup by name.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">phone</span>[<span style="color:#2d7a00;">"Anu"</span>] = <span style="color:#2d7a00;">"9876543210"</span>
    </div>
  </div>

  <div v-click class="card card-blue">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-blue">Dict</span>
      <div class="slide-h3" style="color:var(--blue);">Inventory System</div>
    </div>
    <div class="body-text" style="margin-top:4px;">Each SKU maps to count and price.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">stock</span>[<span style="color:#2d7a00;">"SKU01"</span>] = {<span style="color:#2d7a00;">"qty"</span>:<span style="color:#b45309;">50</span>}
    </div>
  </div>

  <div v-click class="card card-green">
    <div style="display:flex;gap:8px;align-items:center;">
      <span class="pill pill-green">Set</span>
      <div class="slide-h3" style="color:var(--green);">Unique Visitor Tracking</div>
    </div>
    <div class="body-text" style="margin-top:4px;">A set stores each user ID only once — perfect for counts.</div>
    <div class="code-block" style="margin-top:6px;font-size:.7rem;">
      <span style="color:#0e6ead;">visitors</span>.<span style="color:#0e6ead;">add</span>(<span style="color:#0e6ead;">user_id</span>)
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
