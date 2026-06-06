---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two sentences as strings. Write a Python program to count the frequency of each word in the sentence using a dictionary and print the word with the highest frequency.' },
  { text: '<b>Input 1:</b> <code>"the cat sat on the mat the cat"</code>' },
  { text: '<b>Input 2:</b> <code>"apple banana apple orange banana apple"</code>' },
  { text: '<b>Expected Output:</b> <code>Frequency : {"the": 3, "cat": 2, "sat": 1, "on": 1, "mat": 1}</code><br><code>Most Frequent : the → 3 times</code><br><code>Frequency : {"apple": 3, "banana": 2, "orange": 1}</code><br><code>Most Frequent : apple → 3 times</code>' }
]
</script>
<Slide
  topic="Python Dictionary"
  sub-topic="Practice Problem 5"
  :contents="contents"
/>
