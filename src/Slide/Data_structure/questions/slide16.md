---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two dictionaries containing student names and their marks. Write a Python program to access the mark of a specific student, update it with a new mark, and print the updated dictionary.' },
  { text: '<b>Input 1:</b> <code>{"Alice": 78, "Bob": 85, "Carol": 90}</code>, update: <code>"Bob" → 95</code>' },
  { text: '<b>Input 2:</b> <code>{"Tom": 60, "Jerry": 72, "Spike": 88}</code>, update: <code>"Tom" → 75</code>' },
  { text: '<b>Expected Output:</b> <code>Updated Dict : {"Alice": 78, "Bob": 95, "Carol": 90}</code><br><code>Updated Dict : {"Tom": 75, "Jerry": 72, "Spike": 88}</code>' }
]
</script>
<Slide
  topic="Python Dictionary"
  sub-topic="Practice Problem 1"
  :contents="contents"
/>
