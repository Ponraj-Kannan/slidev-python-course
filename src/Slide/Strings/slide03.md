<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">String <span class="highlight">Characteristics</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-red" style="border-radius:10px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--red-dark);margin-bottom:6px;">Immutable — Cannot Be Changed</div>
    <div style="font-size:.74rem;color:var(--slate);line-height:1.6;">Once created, a string's characters <strong>cannot be modified</strong> in place. You must create a new string instead.</div>
    <div style="background:#fff8f8;border-radius:8px;padding:10px 12px;margin-top:8px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"hello"</span><br>
      <span style="color:#6b7280;"># s[0] = "H"  ← TypeError! Cannot modify</span><br>
      <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Hello"</span> &nbsp;&nbsp;<span style="color:#6b7280;"># Correct: assign a new string</span>
    </div>
  </div>

  <div v-click class="card-blue" style="border-radius:10px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--blue);margin-bottom:6px;">Ordered Sequence</div>
    <div style="font-size:.74rem;color:var(--slate);line-height:1.6;">Characters in a string maintain a <strong>fixed order</strong>. <span class="mono">"abc"</span> is always <span class="mono">a</span>, then <span class="mono">b</span>, then <span class="mono">c</span> — never shuffled.</div>
    <div style="background:#ebf8ff;border-radius:8px;padding:10px 12px;margin-top:8px;font-family:'Fira Code',monospace;font-size:.7rem;line-height:1.9;">
      <span style="color:#0e6ead;">s</span> = <span style="color:#2d7a00;">"Python"</span><br>
      <span style="color:#6b7280;"># P is always at position 0</span><br>
      <span style="color:#6b7280;"># n is always at position 5</span>
    </div>
  </div>

</div>

<div class="flex-col">

  <div v-after class="card-green" style="border-radius:10px;">
    <div style="font-size:.78rem;font-weight:600;color:var(--green);margin-bottom:6px;">Indexing — Every Character Has an Address</div>
    <div style="font-size:.74rem;color:var(--slate);line-height:1.5;margin-bottom:8px;">Python assigns an <strong>index number</strong> to every character. Positive indices go left to right; negative indices go right to left.</div>
    <div style="background:#f0fff4;border-radius:8px;padding:12px;font-family:'Fira Code',monospace;font-size:.68rem;">
      <div style="margin-bottom:6px;color:var(--slate);text-align:center;font-weight:600;">"P y t h o n"</div>
      <div style="display:grid;grid-template-columns:repeat(6,1fr);gap:4px;text-align:center;">
        <div v-click style="background:var(--white);border:1px solid var(--green);border-radius:5px;padding:5px 2px;font-weight:600;color:var(--navy);">P</div>
        <div v-after style="background:var(--white);border:1px solid var(--green);border-radius:5px;padding:5px 2px;font-weight:600;color:var(--navy);">y</div>
        <div v-after style="background:var(--white);border:1px solid var(--green);border-radius:5px;padding:5px 2px;font-weight:600;color:var(--navy);">t</div>
        <div v-after style="background:var(--white);border:1px solid var(--green);border-radius:5px;padding:5px 2px;font-weight:600;color:var(--navy);">h</div>
        <div v-after style="background:var(--white);border:1px solid var(--green);border-radius:5px;padding:5px 2px;font-weight:600;color:var(--navy);">o</div>
        <div v-after style="background:var(--white);border:1px solid var(--green);border-radius:5px;padding:5px 2px;font-weight:600;color:var(--navy);">n</div>
        <div style="font-size:.62rem;color:var(--blue);font-weight:600;">0</div>
        <div style="font-size:.62rem;color:var(--blue);font-weight:600;">1</div>
        <div style="font-size:.62rem;color:var(--blue);font-weight:600;">2</div>
        <div style="font-size:.62rem;color:var(--blue);font-weight:600;">3</div>
        <div style="font-size:.62rem;color:var(--blue);font-weight:600;">4</div>
        <div style="font-size:.62rem;color:var(--blue);font-weight:600;">5</div>
        <div style="font-size:.62rem;color:var(--red-dark);font-weight:600;">-6</div>
        <div style="font-size:.62rem;color:var(--red-dark);font-weight:600;">-5</div>
        <div style="font-size:.62rem;color:var(--red-dark);font-weight:600;">-4</div>
        <div style="font-size:.62rem;color:var(--red-dark);font-weight:600;">-3</div>
        <div style="font-size:.62rem;color:var(--red-dark);font-weight:600;">-2</div>
        <div style="font-size:.62rem;color:var(--red-dark);font-weight:600;">-1</div>
      </div>
      <div style="display:flex;justify-content:space-between;margin-top:8px;">
        <span style="color:var(--blue);font-size:.64rem;">← Positive indices →</span>
        <span style="color:var(--red-dark);font-size:.64rem;">← Negative indices →</span>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:4px;">
    <div><strong>Key rule:</strong> For a string of length <span class="mono">n</span>, valid indices are <span class="mono">0</span> to <span class="mono">n-1</span> (positive) and <span class="mono">-1</span> to <span class="mono">-n</span> (negative).</div>
  </div>

</div>

</div>

  </template>
</Slide2>
