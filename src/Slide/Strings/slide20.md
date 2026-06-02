---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a program that takes a string from the user and prints: (a) each character on a new line with its index, (b) total count of uppercase letters, and (c) the string with all spaces removed.' },
  { text: '<b>Input:</b> <code>word = "Hello World"</code>' },
  { text: '<b>Expected Output:</b> <code>[0]=H [1]=e [2]=l [3]=l [4]=o [5]=&nbsp;&nbsp;[6]=W [7]=o [8]=r [9]=l [10]=d<br>Uppercase letters: 2<br>No spaces: HelloWorld</code>' },
  { text: '<b>Key Concepts:</b> Use <code>enumerate()</code> to get both the index and character. Use <code>ch.isupper()</code> to check for uppercase letters. Build a new string by concatenating characters that are not spaces.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Iteration — Test Yourself!"
  :contents="contents"
/>