---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Read a character from the user and print its ASCII value, whether it is uppercase, lowercase, or a digit, and its opposite-case character (if it is a letter).' },
  { text: '<b>Input:</b> <code>Enter a character: G</code>' },
  { text: '<b>Expected Output:</b><br><code>ASCII value : 71</code><br><code>Type        : Uppercase letter</code><br><code>Lowercase   : g</code>' },
  { text: '<b>Note:</b> Use ASCII ranges to classify — uppercase: 65–90, lowercase: 97–122, digits: 48–57.' },
  // { text: '<b>Hint:</b> Read with <code>sc.next().charAt(0)</code>. Cast to <code>int</code> for ASCII. Check ranges with <code>if</code>. Convert case by adding or subtracting 32 with <code>(char)</code> cast.', highlight: true },
]
</script>

<Slide
  topic="Type Checking & Conversion"
  sub-topic="Practice Problem"
  :contents="contents"
/>
