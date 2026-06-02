<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a Python program to encrypt a message using the Caesar Cipher technique. Shift each alphabetic character by <code>3</code> positions forward in the alphabet while leaving spaces unchanged.' },
  { text: '<b>Input:</b> <code>message = "HELLO WORLD"</code>' },
  { text: '<b>Expected Output:</b> <code>KHOOR ZRUOG</code>' },
  { text: '<b>Key Concepts:</b> Use <code>ord()</code> to convert characters into ASCII values and <code>chr()</code> to convert them back into characters. Apply a shift of <code>3</code> positions and use the modulo operator (<code>% 26</code>) to handle wrap-around from <code>Z</code> to <code>A</code>. Preserve spaces without modification.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Caesar Cipher — Practice Problem"
  :contents="contents"
/>