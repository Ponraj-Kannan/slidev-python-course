<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a recursive method to calculate base raised to the power of exponent.' },
  { text: '<b>Input:</b> <code>base = 2, exponent = 8</code>' },
  { text: '<b>Expected Output:</b> <code>2^8 = 256</code>' },
  { text: '<b>Note:</b> Use recursion only. Do not use <code>Math.pow()</code>. Assume the exponent is a non-negative integer.', highlight: true },
  // { text: '<b>Hint:</b> Base case: if <code>exp == 0</code>, return 1. Recursive case: return <code>base * power(base, exp - 1)</code>.', highlight: true },
]
</script>

<Slide
  topic="Recursion"
  sub-topic="Practice Problem 4 — Power of a Number"
  :contents="contents"
/>
