---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Loop through numbers from <code>1</code> to <code>10</code> and search for the first number divisible by <code>4</code> and <code>6</code>. If found, print it and stop. If <b>no such number exists</b> in the range, print a not-found message.' },
  { text: '<b>Input:</b> No input required. The range is fixed from <code>1</code> to <code>10</code>.' },
  {
    text: '<b>Expected Output:</b><br><code>No number divisible by both 4 and 6 found in range.</code>'
  }
]
</script>

<Slide
  topic="else with Loops"
  sub-topic="Practice Problem"
  :contents="contents"
/>
