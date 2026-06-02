<script setup>
const contents = [
  { text: '<b>Problem:</b> Accept a sentence from the user and display the following information: total number of characters, total number of words, total number of vowels, whether the sentence starts with a capital letter, and the reversed sentence.' },
  { text: '<b>Input:</b> <code>sentence = input("Enter a sentence: ")</code>' },
  { text: '<b>Expected Output:</b><br><code>Sentence: Hello World</code><br><code>Total Characters: 11</code><br><code>Total Words: 2</code><br><code>Total Vowels: 3</code><br><code>Starts with Capital: True</code><br><code>Reversed: dlroW olleH</code>' },
  { text: '<b>Key Concepts:</b> Use <code>len()</code> to count characters, <code>split()</code> to count words, a <code>for</code> loop to count vowels, <code>isupper()</code> to check whether the first character is uppercase, and <code>[::-1]</code> to reverse the string.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="String Info Dashboard — Practice Problem"
  :contents="contents"
/>