---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take a number as input and repeatedly divide it by 9 until the result becomes a single digit (less than 10). Print the result after each division.' },
  { text: '<b>Input:</b> <code>729</code>' },
  { text: '<b>Expected Output:</b><br><code>729 / 9 = 81</code><br><code>81 / 9 = 9</code><br><code>Result: 9</code>' },
  // { text: '<b>Note:</b> Use a <b>while</b> loop. The loop should continue as long as the number is greater than or equal to 10.' },
  // { text: '<b>Hint:</b> Use <code>while (n >= 10)</code> and divide <code>n = n / 9</code> inside the loop. Print the value of <code>n</code> after each step.', highlight: true },
]
</script>

<Slide
  topic="While Loop"
  sub-topic="Practice Problem"
  :contents="contents"
/>
