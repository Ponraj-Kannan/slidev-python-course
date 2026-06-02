---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> A student scored <code>87.5</code> out of <code>100</code>. Using f-strings, print: <code>"Student: Alice | Score: 87.50 / 100 | Grade: B"</code>.' },
  { text: '<b>Input:</b> <code>name = "Alice", score = 87.5, total = 100, grade = "B"</code>' },
  { text: '<b>Expected Output:</b> <code>Student: Alice | Score: 87.50 / 100 | Grade: B</code><br><br><b>Bonus:</b> Print the percentage formatted to <code>1</code> decimal place.' },
  { text: '<b>Key Concepts:</b> f-strings embed expressions inside <code>{}</code>. Use <code>:.2f</code> for 2 decimal places. f-strings can include any valid Python expression, including arithmetic operations.' }
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="String Formatting — Test Yourself!"
  :contents="contents"
/>