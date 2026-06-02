---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Predict the output of each line without running Python:<br><code>(a) "Hello"[1:4]</code><br><code>(b) "abc" * 3</code><br><code>(c) "  hi  ".strip().upper()</code><br><code>(d) "a,b,c".split(",")</code><br><code>(e) "-".join(["x","y","z"])</code><br><code>(f) f"{3 * 4:.2f}"</code>', highlight: true },
  { text: '<b>Input:</b> Each expression is standalone.' },
  { text: '<b>Expected Output:</b> <code>(a) "ell"<br>(b) "abcabcabc"<br>(c) "HI"<br>(d) ["a", "b", "c"]<br>(e) "x-y-z"<br>(f) "12.00"</code>' },
  { text: '<b>Key Concepts:</b> Slicing stop index is exclusive. String repetition duplicates the string multiple times. Chained methods execute from left to right. <code>split()</code> returns a list, <code>join()</code> combines list elements into a string, and f-strings evaluate expressions before formatting.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Comprehensive Quiz — Test Yourself!"
  :contents="contents"
/>