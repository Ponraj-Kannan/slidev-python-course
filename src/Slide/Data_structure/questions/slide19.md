---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two dictionaries each containing student names and scores. Write a Python program to merge both dictionaries into one and find the student with the highest score.' },
  { text: '<b>Input 1:</b> <code>{"Alice": 88, "Bob": 95}</code>' },
  { text: '<b>Input 2:</b> <code>{"Carol": 73, "David": 99}</code>' },
  { text: '<b>Expected Output:</b> <code>Merged Dict   : {"Alice": 88, "Bob": 95, "Carol": 73, "David": 99}</code><br><code>Top Scorer    : David with 99</code>' }
]
</script>
<Slide
  topic="Python Dictionary"
  sub-topic="Practice Problem 4"
  :contents="contents"
/>
