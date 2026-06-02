---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Calculate and print the sum of all even numbers between 1 and 50.' },
  { text: '<b>Expected Output:</b> <code>Sum of even numbers = 650</code>' },
  { text: '<b>Note:</b> Use a <b>for</b> loop. A number is even if <code>number % 2 == 0</code>.' },
  // { text: '<b>Hint:</b> Declare a variable <code>sum = 0</code> before the loop. Inside the loop, check if <code>i % 2 == 0</code> and add <code>i</code> to <code>sum</code>. Print <code>sum</code> after the loop.', highlight: true },
]
</script>

<Slide
  topic="For Loop"
  sub-topic="Practice Problem"
  :contents="contents"
/>
