<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a recursive method to print the first n terms of the Fibonacci series.' },
  { text: '<b>Input:</b> <code>n = 7</code>' },
  { text: '<b>Expected Output:</b> <code>0 1 1 2 3 5 8</code>' },
  { text: '<b>Note:</b> Use recursion to find each term. Call the method inside a loop in <code>main()</code> to print each term from <code>0</code> to <code>n-1</code>.' },
  // { text: '<b>Hint:</b> Define <code>static int fibonacci(int n)</code>. Base cases: <code>n == 0</code> returns 0, <code>n == 1</code> returns 1. Otherwise return <code>fibonacci(n-1) + fibonacci(n-2)</code>.', highlight: true },
]
</script>

<Slide
  topic="Recursion"
  sub-topic="Practice Problem 2 — Fibonacci"
  :contents="contents"
/>
