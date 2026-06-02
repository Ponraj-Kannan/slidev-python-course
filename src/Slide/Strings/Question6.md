<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a Python program that accepts a user\'s full name and birth year. Generate a username using the first 3 letters of the first name, the last 3 letters of the last name, and the last 2 digits of the birth year. The username should be displayed in lowercase.' },
  { text: '<b>Input:</b> <code>name = "Alice Smith"</code><br><code>year = 2004</code>' },
  { text: '<b>Expected Output:</b> <code>alimit04</code>' },
  { text: '<b>Key Concepts:</b> Use <code>split()</code> to separate the full name into parts, string slicing (<code>[:3]</code> and <code>[-3:]</code>) to extract required characters, <code>str(year)[-2:]</code> to obtain the last two digits of the birth year, and <code>lower()</code> to convert the username to lowercase.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Username Generator — Practice Problem"
  :contents="contents"
/>