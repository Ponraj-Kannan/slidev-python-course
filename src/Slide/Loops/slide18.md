---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — pass STATEMENT + break/continue/pass COMPARISON
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Loop Control">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">pass</span> Statement &amp; Complete Comparison</div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click style="display:flex;align-items:center;gap:8px;margin-bottom:8px;">
    <span style="background:var(--yellow);color:#fff;border-radius:6px;padding:3px 12px;font-family:'Fira Code',monospace;font-weight:700;font-size:.85rem;">pass</span>
    <span class="body-text">— Placeholder, does nothing</span>
  </div>

  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">i</span> <span style="color:#ef5050;">in</span> <span style="color:#2d7a00;">range</span>(<span style="color:#b45309;">1</span>, <span style="color:#b45309;">6</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">i</span> == <span style="color:#b45309;">3</span>:</span>
    <span style="padding-left:40px;display:block;"><span style="color:#ef5050;">pass</span> <span style="color:#6b7280;"># nothing here yet</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">i</span>)</span>
  </div>

  <div v-click class="output-box" style="font-size:.72rem;">
    1 &nbsp; 2 &nbsp; 3 &nbsp; 4 &nbsp; 5 &nbsp; <span style="color:#6b7280;">(all printed — pass does nothing)</span>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div><strong>pass</strong> is useful when you want an empty block syntactically — Python does not allow empty blocks!</div>
  </div>
</div>

<div class="flex-col">
  <div v-click class="section-label">break vs continue vs pass</div>

  <div>
    <table class="cmp-table">
      <thead v-after>
        <tr><th>Statement</th><th>Effect on Loop</th><th>Loop Continues?</th></tr>
      </thead>
      <tbody>
        <tr v-click>
          <td><span class="mono" style="color:var(--red-dark);font-weight:700;">break</span></td>
          <td>Exits the loop completely</td>
          <td class="no">No</td>
        </tr>
        <tr v-click>
          <td><span class="mono" style="color:var(--green);font-weight:700;">continue</span></td>
          <td>Skips the current iteration</td>
          <td class="yes">Yes (next iteration)</td>
        </tr>
        <tr v-click>
          <td><span class="mono" style="color:var(--yellow);font-weight:700;">pass</span></td>
          <td>Does nothing — placeholder</td>
          <td class="yes">Yes (normally)</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div v-click class="card card-navy" style="margin-top:10px;">
    <div style="font-size:.7rem;color:var(--slate);line-height:1.7;">
      <strong style="color:var(--red-dark);">break</strong> — "I found what I need, stop searching"<br>
      <strong style="color:var(--green);">continue</strong> — "Skip this one, check the next"<br>
      <strong style="color:var(--orange);">pass</strong> — "I'll fill this logic in later"
    </div>
  </div>
</div>

</div>

  </template>
</Slide2>
