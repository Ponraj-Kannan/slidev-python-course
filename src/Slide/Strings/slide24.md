
<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practice <span class="highlight">Programs</span> — Part 2</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="activity-box">
    <div class="act-title">Program 6 — Username Generator</div>
    <div class="act-task">
      Accept a full name and birth year from the user. Auto-generate a username: first 3 letters of first name + last 3 letters of last name + last 2 digits of birth year, all lowercase.
    </div>
    <div class="hint">// { text: 'Hint: parts = name.split(); username = (parts[0][:3] + parts[-1][-3:] + str(year)[-2:]).lower()', highlight: true }</div>
  </div>

  <div v-click class="activity-box" style="margin-top:8px;">
    <div class="act-title">Program 7 — Anagram Detector</div>
    <div class="act-task">
      Check if two words entered by the user are <strong>anagrams</strong> (contain the same letters, just rearranged). Ignore case and spaces.
    </div>
    <div class="hint">// { text: 'Hint: Sort the letters of both words and compare: sorted(w1.lower()) == sorted(w2.lower())', highlight: true }</div>
  </div>

  <div v-click class="activity-box" style="margin-top:8px;">
    <div class="act-title">Program 8 — Sentence Titlecase Fixer</div>
    <div class="act-task">
      Accept a mixed-case sentence and fix it: capitalise only the first letter of each sentence (ends with <span class="mono">.</span> or <span class="mono">!</span>). Output the corrected paragraph.
    </div>
    <div class="hint">// { text: 'Hint: Split on \". \", apply .capitalize() to each part, then rejoin with \". \".join()', highlight: true }</div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="activity-box">
    <div class="act-title">Program 9 — URL Slug Creator</div>
    <div class="act-task">
      Convert a blog post title to a URL-friendly slug: lowercase, spaces replaced with hyphens, remove special characters (<span class="mono">,</span> <span class="mono">!</span> <span class="mono">?</span> <span class="mono">'</span> etc.).
    </div>
    <div class="hint">// { text: 'Hint: Use .lower().replace(\" \", \"-\"), then loop and keep only alphanumeric and hyphen chars.', highlight: true }</div>
  </div>

  <div v-click class="activity-box" style="margin-top:8px;">
    <div class="act-title">Program 10 — String Compression</div>
    <div class="act-task">
      Compress a string using <strong>run-length encoding</strong>: replace consecutive repeated characters with the character followed by its count. E.g. <span class="mono">"aaabbc"</span> → <span class="mono">"a3b2c1"</span>.
    </div>
    <div class="hint">// { text: 'Hint: Loop through the string, compare each char to the previous, maintain a count, and build the result string.', highlight: true }</div>
  </div>

  <div v-click class="callout callout-info" style="margin-top:8px; margin-bottom:40px">
    <div><strong>Tip:</strong> For Programs 6–10, test edge cases — empty strings, single characters, strings with only spaces. Robust programs handle all inputs gracefully.</div>
  </div>

</div>

</div>

  </template>
</Slide2>
