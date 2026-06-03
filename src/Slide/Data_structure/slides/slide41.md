<Slide2 topic="When to Use Which Collection">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">When</span> to Use Which Collection</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-red">
    <div class="slide-h3" style="color:var(--red-dark);">Use a List when...</div>
    <ul class="body-text" style="margin:6px 0 0 16px;padding:0;">
      <li>Order matters</li>
      <li>Data may change (add / remove / update)</li>
      <li>You need indexing and slicing</li>
    </ul>
    <div class="small-text" style="margin-top:6px;color:var(--muted);"><strong>Example:</strong> Shopping cart, student marks</div>
  </div>

  <div v-click class="card card-orange">
    <div class="slide-h3" style="color:var(--orange);">Use a Tuple when...</div>
    <ul class="body-text" style="margin:6px 0 0 16px;padding:0;">
      <li>Data is fixed and read-only</li>
      <li>You want speed and safety</li>
      <li>You need to return multiple values</li>
    </ul>
    <div class="small-text" style="margin-top:6px;color:var(--muted);"><strong>Example:</strong> Coordinates, RGB color</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-green">
    <div class="slide-h3" style="color:var(--green);">Use a Set when...</div>
    <ul class="body-text" style="margin:6px 0 0 16px;padding:0;">
      <li>You only care about uniqueness</li>
      <li>Order does not matter</li>
      <li>You need fast membership tests</li>
    </ul>
    <div class="small-text" style="margin-top:6px;color:var(--muted);"><strong>Example:</strong> Unique visitors, common items</div>
  </div>

  <div v-click class="card card-blue">
    <div class="slide-h3" style="color:var(--blue);">Use a Dictionary when...</div>
    <ul class="body-text" style="margin:6px 0 0 16px;padding:0;">
      <li>Data has a label -> value mapping</li>
      <li>You need fast lookup by key</li>
      <li>You're modelling a record</li>
    </ul>
    <div class="small-text" style="margin-top:6px;color:var(--muted);"><strong>Example:</strong> Phone book, JSON data</div>
  </div>
</div>

</div>

  </template>
</Slide2>
