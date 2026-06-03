---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two sets of integers. Write a Python program to find the difference between the two sets and the symmetric difference, then print both results.' },
  { text: '<b>Input 1:</b> <code>{10, 20, 30, 40, 50}</code>' },
  { text: '<b>Input 2:</b> <code>{30, 40, 50, 60, 70}</code>' },
  { text: '<b>Expected Output:</b> <code>Difference (A-B)          : {10, 20}</code><br><code>Symmetric Difference (A^B) : {10, 20, 60, 70}</code>' }
]
</script>
<Slide
  topic="Python Sets"
  sub-topic="Practice Problem 3"
  :contents="contents"
/>
