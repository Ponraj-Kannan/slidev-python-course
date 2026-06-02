<script setup>
const contents = [
  { text: '<b>Problem:</b> Write a recursive method to find the sum of digits of a given number.' },
  { text: '<b>Input:</b> <code>n = 1234</code>' },
  { text: '<b>Expected Output:</b> <code>Sum of digits = 10</code>  (1 + 2 + 3 + 4)' },
  { text: '<b>Note:</b> Use recursion only. Do not use a loop or convert the number to a String.' ,highlight: true },
  // { text: '<b>Hint:</b> The last digit is <code>n % 10</code>. The remaining number is <code>n / 10</code>. Base case: if <code>n == 0</code>, return 0. Otherwise return <code>(n % 10) + sumOfDigits(n / 10)</code>.', highlight: true },
]
</script>

<Slide
  topic="Recursion"
  sub-topic="Practice Problem 3 — Sum of Digits"
  :contents="contents"
/>
