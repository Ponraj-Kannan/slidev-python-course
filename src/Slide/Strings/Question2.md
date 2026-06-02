<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a Python program that asks the user to enter a word or phrase and checks whether it is a palindrome. The program should ignore letter case and spaces while performing the comparison.' },
  { text: '<b>Input:</b> <code>word = input("Enter a word or phrase: ")</code>' },
  { text: '<b>Expected Output:</b><br><code>Input: "Madam" → Palindrome</code><br><code>Input: "Never Odd Or Even" → Palindrome</code><br><code>Input: "Python" → Not a Palindrome</code>' },
  { text: '<b>Key Concepts:</b> Use <code>strip()</code>, <code>lower()</code>, and <code>replace(" ", "")</code> to normalize the input. Reverse the string using <code>[::-1]</code> and compare it with the original cleaned string to determine whether it is a palindrome.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Palindrome Checker — Practice Problem"
  :contents="contents"
/>