---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two dictionaries containing product names and their prices. Write a Python program to iterate through the dictionary and print all keys, all values, and all key-value pairs separately.' },
  { text: '<b>Input 1:</b> <code>{"Apple": 50, "Banana": 20, "Cherry": 80}</code>' },
  { text: '<b>Input 2:</b> <code>{"Pen": 10, "Notebook": 40, "Eraser": 5}</code>' },
  { text: '<b>Expected Output:</b> <code>Keys   : Apple, Banana, Cherry</code><br><code>Values : 50, 20, 80</code><br><code>Items  : Apple→50, Banana→20, Cherry→80</code>' }
]
</script>
<Slide
  topic="Python Dictionary"
  sub-topic="Practice Problem 3"
  :contents="contents"
/>
