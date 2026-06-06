<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Introduction to <span class="highlight">Strings</span></div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="card-navy" style="border-radius:10px;">
    <div style="font-size:.82rem;line-height:1.6;color:var(--slate);">
      A <strong style="color:var(--red);">string</strong> is a <strong>sequence of characters</strong> enclosed in quotes. Characters include letters, digits, spaces, punctuation, and special symbols.
    </div>
  </div>

  <div v-click class="callout callout-warn">
    <div><strong>Think of it like this:</strong> A string is like a <strong>necklace of beads</strong> — each bead is a character, and the whole necklace is the string.</div>
  </div>

  <div v-click style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:14px;font-family:'Fira Code',monospace;font-size:.74rem;line-height:2;">
    <span style="color:#6b7280;"># All of these are strings</span><br>
    <span style="color:#0e6ead;">name</span>    = <span style="color:#2d7a00;">"Alice"</span><br>
    <span style="color:#0e6ead;">city</span>    = <span style="color:#2d7a00;">'Chennai'</span><br>
    <span style="color:#0e6ead;">digit</span>   = <span style="color:#2d7a00;">"42"</span> &nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#6b7280;"># "42" is a string, not a number</span><br>
    <span style="color:#0e6ead;">empty</span>   = <span style="color:#2d7a00;">""</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#6b7280;"># empty string is valid</span><br>
    <span style="color:#0e6ead;">message</span> = <span style="color:#2d7a00;">"Hello, World!"</span>
  </div>

  <div v-click class="callout callout-success">
    <div>In Python, strings are objects of type <span class="mono" style="color:var(--navy);">str</span>. Use <span class="mono">type()</span> to verify: <span class="mono">type("hello")</span> → <span class="mono" style="color:var(--green);">&lt;class 'str'&gt;</span></div>
  </div>

</div>

<div class="flex-col">
  <div class="section-label" v-click>Why Strings Matter</div>

  <div style="display:flex;flex-direction:column;gap:8px;" v-click>
    <div class="card" style="display:flex;gap:10px;align-items:flex-start;">
      <div class="icon-circle ic-red" style="font-size:.9rem;">💬</div>
      <div>
        <div style="font-size:.75rem;font-weight:600;color:var(--navy);">User Interaction</div>
        <div style="font-size:.7rem;color:var(--slate);">Names, messages, prompts, and responses are all strings</div>
      </div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:flex-start;">
      <div class="icon-circle ic-blue" style="font-size:.9rem;">📂</div>
      <div>
        <div style="font-size:.75rem;font-weight:600;color:var(--navy);">File & Data Handling</div>
        <div style="font-size:.7rem;color:var(--slate);">File paths, CSV fields, database records use strings</div>
      </div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:flex-start;">
      <div class="icon-circle ic-green" style="font-size:.9rem;">🌐</div>
      <div>
        <div style="font-size:.75rem;font-weight:600;color:var(--navy);">Web & APIs</div>
        <div style="font-size:.7rem;color:var(--slate);">URLs, HTML, JSON keys and values are all strings</div>
      </div>
    </div>
    <div class="card" style="display:flex;gap:10px;align-items:flex-start;">
      <div class="icon-circle ic-orange" style="font-size:.9rem;">🔐</div>
      <div>
        <div style="font-size:.75rem;font-weight:600;color:var(--navy);">Security</div>
        <div style="font-size:.7rem;color:var(--slate);">Passwords, tokens, and validation all rely on strings</div>
      </div>
    </div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:6px;">
    <div>Strings are one of the most-used data types in Python — mastering them unlocks real-world programming power!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
