---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two lists that contain duplicate values. Write a Python program to use a set to remove all duplicates from each list, then print the total number of duplicates removed and the final unique elements.' },
  { text: '<b>Input 1:</b> <code>[3, 5, 3, 7, 9, 5, 7, 3]</code>' },
  { text: '<b>Input 2:</b> <code>[1, 4, 4, 6, 8, 6, 1, 8, 8]</code>' },
  { text: '<b>Expected Output:</b> <code>Unique Elements  : {3, 5, 7, 9}</code><br><code>Duplicates Removed : 4</code><br><code>Unique Elements  : {1, 4, 6, 8}</code><br><code>Duplicates Removed : 5</code>' }
]
</script>
<Slide
  topic="Python Sets"
  sub-topic="Practice Problem 5"
  :contents="contents"
/>
