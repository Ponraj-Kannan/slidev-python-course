---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two tuples. Since tuples are immutable, write a Python program to convert each tuple to a list, replace the smallest value with 0, then convert it back to a tuple and print it.' },
  { text: '<b>Input 1:</b> <code>(5, 3, 8, 1, 7)</code>' },
  { text: '<b>Input 2:</b> <code>(12, 4, 9, 6, 2)</code>' },
  { text: '<b>Expected Output:</b> <code>Updated Tuple : (5, 3, 8, 0, 7)</code><br><code>Updated Tuple : (12, 4, 9, 6, 0)</code>' }
]
</script>
<Slide
  topic="Python Tuples"
  sub-topic="Practice Problem 4"
  :contents="contents"
/>
