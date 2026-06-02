<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a Python program that accepts a user\'s first name, last name, age, and city. Generate a neatly formatted name card using f-strings, aligned labels, and a border made of <code>=</code> characters.' },
  { text: '<b>Input:</b> <code>first_name = "Alice"</code><br><code>last_name = "Smith"</code><br><code>age = 21</code><br><code>city = "Chennai"</code>' },
  { text: '<b>Expected Output:</b><br><code>==============================<br>First Name : Alice<br>Last Name  : Smith<br>Age        : 21<br>City       : Chennai<br>==============================</code>' },
  { text: '<b>Key Concepts:</b> Use f-strings for string formatting, alignment specifiers such as <code>{label:&lt;10}</code> for neat column layout, and string repetition (<code>"=" * 30</code>) to create decorative borders.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Name Card Generator — Practice Problem"
  :contents="contents"
/>