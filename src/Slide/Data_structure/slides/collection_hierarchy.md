<Slide2 topic="Four Collection Types — Overview">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">The <span class="highlight">Collection Hierarchy</span></div>

<div v-click style="margin-top:12px; display:flex; justify-content:center; align-items:center; flex-direction:column">
  <div style="background:var(--white);border:1px solid var(--border);border-radius:10px;padding:14px;">

```mermaid {scale: 0.65}
graph LR
    A[Python Collections] --> B[Sequence]
    A --> C[Set]
    A --> D[Mapping]
    B --> B1[list - mutable]
    B --> B2[tuple - immutable]
    C --> C1[set - mutable]
    C --> C2[frozenset - immutable]
    D --> D1[dict - mutable]
```
<!-- <img src="https://www.hshv.org/wp-content/uploads/2018/08/Henry.jpg" style="max-height:40vh"/> -->
  </div>
</div>

  </template>
</Slide2>
