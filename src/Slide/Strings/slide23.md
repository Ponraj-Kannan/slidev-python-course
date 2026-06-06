

<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practice <span class="highlight">Programs</span> — Part 1</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="activity-box">
    <div class="act-title">Program 1 — String Info Dashboard</div>
    <div class="act-task">
      Accept a sentence from the user and display: total characters, total words, total vowels, whether it starts with a capital letter, and the sentence reversed.
    </div>
    <div class="hint">// { text: 'Hint: Use len(), split(), for loop with in, isupper() on first char, and [::-1]', highlight: true }</div>
  </div>

  <div v-click class="activity-box" style="margin-top:8px;">
    <div class="act-title">Program 2 — Palindrome Checker</div>
    <div class="act-task">
      Ask the user to enter a word. Check if it is a <strong>palindrome</strong> (reads the same forwards and backwards). Ignore case and spaces.
    </div>
    <div class="hint">// { text: 'Hint: cleaned = word.strip().lower().replace(\" \", \"\"), then compare cleaned == cleaned[::-1]', highlight: true }</div>
  </div>

  <div v-click class="activity-box" style="margin-top:8px;">
    <div class="act-title">Program 3 — Word Frequency Counter</div>
    <div class="act-task">
      Given a paragraph string, count how many times each unique word appears. Print results in the format: <span class="mono">word → N times</span>. (Use a dictionary and split.)
    </div>
    <div class="hint">// { text: 'Hint: words = text.lower().split(), then loop and use dict.get(word, 0) + 1', highlight: true }</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="activity-box">
    <div class="act-title">Program 4 — Caesar Cipher</div>
    <div class="act-task">
      Encrypt a message using the Caesar cipher: shift each letter by <strong>3 positions</strong> forward in the alphabet. Leave spaces unchanged.
    </div>
    <div class="hint">// { text: 'Hint: Use ord() to get ASCII value, shift by 3, use chr() to convert back. Handle wrap-around with % 26.', highlight: true }</div>
  </div>

  <div v-click class="activity-box" style="margin-top:8px;">
    <div class="act-title">Program 5 — Name Card Generator</div>
    <div class="act-task">
      Accept first name, last name, age, and city from the user. Generate a formatted name card using f-strings with proper alignment, a border of <span class="mono">=</span> signs, and all fields labelled neatly.
    </div>
    <div class="hint">// { text: 'Hint: Use f\"{label:<10}{value}\" for aligned fields and \"=\" * 30 for the border lines.', highlight: true }</div>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:8px; margin-bottom:40px">
    <div><strong>Challenge:</strong> Modify Program 2 to check if a full sentence is a palindrome by removing all punctuation and spaces before comparing.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
