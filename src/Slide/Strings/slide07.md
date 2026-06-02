---
transition: slide-up
---
<script setup>
const contents = [
  { text: '<b>Problem:</b> Given <code>word = "Python"</code>, access and print the first character, third character, last character, and second-last character using indexing.' },
  { text: '<b>Input:</b> <code>word = "Python"</code>' },
  { text: '<b>Expected Output:</b> <code>word[0] → P<br>word[2] → t<br>word[-1] → n<br>word[-2] → o</code>' },
  { text: '<b>Key Concepts:</b> Characters in a string can be accessed using indexing. Positive indexing starts from <code>0</code> on the left, while negative indexing starts from <code>-1</code> on the right.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Accessing Characters — Test Yourself!"
  :contents="contents"
/>