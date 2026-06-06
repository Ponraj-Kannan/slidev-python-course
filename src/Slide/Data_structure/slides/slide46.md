<Slide2 topic="Quick Recap — All Four Collections">
  <template #content>
<div class="slide-h1" style="margin-bottom:10px;">Quick <span class="highlight">Recap</span> — Snapshot</div>
<div v-click style="margin-top:12px; display:flex; justify-content:center;">
```mermaid {scale: 0.6}
graph TD
    Q[Need to store many values?]
    Q --> L{Order &amp; duplicates allowed?}
    L -- Yes, mutable --> LIST[List]
    L -- Yes, fixed --> TUPLE[Tuple]
    L -- No, unique --> SET[Set]
    L -- Need key:value --> DICT[Dictionary]
```
</div>
  </template>
</Slide2>
