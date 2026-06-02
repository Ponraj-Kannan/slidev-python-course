<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a recursive method to find the factorial of a given number.' },
  { text: '<b>Input:</b> <code>n = 6</code>' },
  { text: '<b>Expected Output:</b> <code>Factorial of 6 = 720</code>' },
  { text: '<b>Note:</b> Use recursion only. Do not use any loop. Handle <code>n = 0</code> as a base case returning 1.' },
  // { text: '<b>Hint:</b> Define <code>static int factorial(int n)</code>. If <code>n == 0</code> return 1. Otherwise return <code>n * factorial(n - 1)</code>.', highlight: true },
]
</script>

<Slide
  topic="Recursion"
  sub-topic="Practice Problem 1 — Factorial"
  :contents="contents"
/>
