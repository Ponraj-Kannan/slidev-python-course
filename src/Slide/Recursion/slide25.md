<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a recursive method to find the power of a number using a base value and an exponent value.' },
  { text: '<b>Input:</b> <code>base = 2, exponent = 5</code>' },
  { text: '<b>Expected Output:</b> <code>32</code>' },
  { text: '<b>Note:</b> Use recursion to calculate the result. Multiply the base value by the result of the recursive call with the exponent decreased by 1 until the exponent becomes 0.' },
  // { text: '<b>Hint:</b> Define <code>static int power(int base, int exponent)</code>. Base case: <code>exponent == 0</code> returns 1. Otherwise return <code>base * power(base, exponent - 1)</code>.', highlight: true },
]
</script>

<Slide
  topic="Recursion"
  sub-topic="Practice Problem 6 — Power of a Number"
  :contents="contents"
/>