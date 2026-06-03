---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two pairs of sets. Write a Python program to check whether the first set is a subset of the second set and whether the second set is a superset of the first set, then print the results.' },
  { text: '<b>Input 1:</b> <code>A = {2, 4, 6}</code>, <code>B = {1, 2, 3, 4, 5, 6}</code>' },
  { text: '<b>Input 2:</b> <code>A = {7, 8, 9}</code>, <code>B = {1, 2, 3, 4, 5}</code>' },
  { text: '<b>Expected Output:</b> <code>Is A subset of B?    : True</code><br><code>Is B superset of A?  : True</code><br><code>Is A subset of B?    : False</code><br><code>Is B superset of A?  : False</code>' }
]
</script>
<Slide
  topic="Python Sets"
  sub-topic="Practice Problem 4"
  :contents="contents"
/>
