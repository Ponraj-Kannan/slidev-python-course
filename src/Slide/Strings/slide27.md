---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Spot and fix 3 bugs in the following code:<br><code>(1) print("Score: " + 95)</code><br><code>(2) s = "hello"; s[0] = "H"; print(s)</code><br><code>(3) s = "python"; s.upper(); print(s)</code>' },
  { text: '<b>Input:</b> Each line is a standalone buggy snippet.' },
  { text: '<b>Expected (Fixed) Output:</b> <code>(1) print("Score: " + str(95)) → Score: 95<br>(2) s = "H" + s[1:] → Hello<br>(3) s = s.upper() → PYTHON</code>' },
  { text: '<b>Key Concepts:</b> <code>str + int</code> causes a <code>TypeError</code>—use <code>str()</code> or f-strings. Strings are immutable, so use slicing to create a modified string. String methods return new strings, so always reassign the result when needed.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Mistakes — Test Yourself!"
  :contents="contents"
/>