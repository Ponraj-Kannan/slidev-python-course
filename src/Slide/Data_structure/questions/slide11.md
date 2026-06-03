---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two sets of numbers. Write a Python program to add a new element to each set and remove an existing element from each set, then print the updated sets.' },
  { text: '<b>Input 1:</b> <code>{10, 20, 30, 40}</code>, add: <code>50</code>, remove: <code>20</code>' },
  { text: '<b>Input 2:</b> <code>{5, 15, 25, 35}</code>, add: <code>45</code>, remove: <code>15</code>' },
  { text: '<b>Expected Output:</b> <code>Updated Set : {10, 30, 40, 50}</code><br><code>Updated Set : {5, 25, 35, 45}</code>' }
]
</script>
<Slide
  topic="Python Sets"
  sub-topic="Practice Problem 1"
  :contents="contents"
/>
