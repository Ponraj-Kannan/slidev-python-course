<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a recursive method to check whether a given string is a palindrome.' },
  { text: '<b>Input:</b> <code>"racecar"</code> → <code>true</code>' },
  { text: '<b>Input:</b> <code>"hello"</code> → <code>false</code>' },
  { text: '<b>Note:</b> A string is a palindrome if it reads the same forwards and backwards. Use recursion only.', highlight: true },
  // { text: '<b>Hint:</b> Compare the first character (<code>charAt(0)</code>) and last character (<code>charAt(length-1)</code>). If they differ, return false. Otherwise, recurse on the middle substring using <code>substring(1, length-1)</code>. Base case: length 0 or 1 returns true.', highlight: true },
]
</script>

<Slide
  topic="Recursion"
  sub-topic="Practice Problem 5 — Palindrome Check"
  :contents="contents"
/>
