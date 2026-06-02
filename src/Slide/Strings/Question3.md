<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a Python program that accepts a paragraph and counts how many times each unique word appears. Display the result in the format <code>word → N times</code>.' },
  { text: '<b>Input:</b> <code>text = "Python is easy and Python is powerful"</code>' },
  { text: '<b>Expected Output:</b><br><code>python → 2 times</code><br><code>is → 2 times</code><br><code>easy → 1 time</code><br><code>and → 1 time</code><br><code>powerful → 1 time</code>' },
  { text: '<b>Key Concepts:</b> Use <code>lower()</code> to make the comparison case-insensitive, <code>split()</code> to separate the paragraph into words, and a dictionary to store word frequencies. Use <code>dict.get(word, 0) + 1</code> to update the count of each word.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="Word Frequency Counter — Practice Problem"
  :contents="contents"
/>