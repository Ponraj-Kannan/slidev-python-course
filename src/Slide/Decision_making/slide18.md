---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 21 — PASS vs COMMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Decision-making statements">
  <template #content>
<div class="slide-h1" style="margin-bottom:14px;"><span class="highlight">pass</span> vs Comments — What's the Difference?</div>

<div class="g2" style="gap:14px;">

<div class="flex-col" style="gap:10px;">
  <div v-click class="card card-orange">
    <div style="display:flex;gap:10px;align-items:center;margin-bottom:8px;">
      <div class="slide-h2">pass — A Statement</div>
    </div>
    <div class="flex-col" style="gap:6px;">
      <div class="body-text">Recognized by the Python <strong>interpreter</strong></div>
      <div class="body-text">Keeps a code block <strong>syntactically valid</strong></div>
      <div class="body-text">Executes (does nothing) at <strong>runtime</strong></div>
      <div class="body-text">can be used in if, loops, functions, classes</div>
    </div>
  </div>

  <div v-click style="background:#ffffff;border-radius:10px;padding:12px 18px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.8;">
    <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">x</span> > <span style="color:#ffd166;">0</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ffd166;">pass</span>&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;">← valid, interpreter sees this</span>
  </div>
</div>

<div class="flex-col" style="gap:10px;">
  <div v-click class="card card-blue">
    <div style="display:flex;gap:10px;align-items:center;margin-bottom:8px;">
      <div class="slide-h2">Comments — Not Code</div>
    </div>
    <div class="flex-col" style="gap:6px;">
      <div class="body-text"><strong>Ignored</strong> by the Python interpreter</div>
      <div class="body-text">Cannot replace a required statement</div>
      <div class="body-text">Used to explain code for humans</div>
      <div class="body-text">Does NOT count as a block statement</div>
    </div>
  </div>

  <div v-click style="background:#ffffff;border-radius:10px;padding:12px 18px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:1.8;">
    <span style="color:#ff79c6;">if</span> <span style="color:#61dafb;">x</span> > <span style="color:#ffd166;">0</span>:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#636e80;"># comment only → SyntaxError!</span>
  </div>
</div>

</div>

<div style="margin-top:12px;">
  <table class="cmp-table" >
    <tr v-click>
      <th>Feature</th>
      <th>pass</th>
      <th># Comment</th>
    </tr>
    <tr v-click>
      <td>Seen by interpreter</td>
      <td class="yes">✅ Yes</td>
      <td class="no">❌ No</td>
    </tr>
    <tr v-click>
      <td>Fills empty block</td>
      <td class="yes">✅ Yes</td>
      <td class="no">❌ No</td>
    </tr>
    <tr v-click>
      <td>Explains code to humans</td>
      <td class="no">❌ No</td>
      <td class="yes">✅ Yes</td>
    </tr>
    <tr v-click>
      <td>Used together?</td>
      <td colspan="2" style="text-align:center;" class="yes">✅ Yes — use both! <code>pass  # TODO: implement</code></td>
    </tr>
  </table>
</div>
  </template>
</Slide2>
