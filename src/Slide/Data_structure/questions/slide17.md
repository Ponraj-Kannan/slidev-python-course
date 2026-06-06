---
transition: fade
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given two dictionaries. Write a Python program to add a new key-value pair to each dictionary and delete an existing key, then print the final dictionary.' },
  { text: '<b>Input 1:</b> <code>{"name": "Alice", "age": 20, "city": "Chennai"}</code>, add: <code>"grade": "A"</code>, delete: <code>"city"</code>' },
  { text: '<b>Input 2:</b> <code>{"name": "Bob", "age": 22, "city": "Delhi"}</code>, add: <code>"grade": "B"</code>, delete: <code>"age"</code>' },
  { text: '<b>Expected Output:</b> <code>Final Dict : {"name": "Alice", "age": 20, "grade": "A"}</code><br><code>Final Dict : {"name": "Bob", "city": "Delhi", "grade": "B"}</code>' }
]
</script>
<Slide
  topic="Python Dictionary"
  sub-topic="Practice Problem 2"
  :contents="contents"
/>
