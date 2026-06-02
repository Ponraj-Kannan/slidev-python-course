---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Loop through numbers from <code>1</code> to <code>20</code>. Find the <b>first</b> number that is divisible by both <code>3</code> and <code>5</code>. Print it and stop the loop immediately.' },
  {
    text: '<b>Expected Output:</b><br><code>15</code>'
  },
  // {
  //   text: '<b>Key Concepts:</b> A number is divisible by both <code>3</code> and <code>5</code> when <code>n % 3 == 0</code> <b>and</b> <code>n % 5 == 0</code>. Use the <b>modulo operator</b> <code>%</code> to check divisibility. Once found, use <code>break</code> to exit the loop immediately without checking remaining numbers.'
  // },
  {
    text: '<b>Note:</b> Use a <b>for</b> loop with <code>range(1, 21)</code> to go through numbers <code>1</code> to <code>20</code>. Inside the loop, use an <b>if</b> condition to check both divisibility conditions together using <code>and</code>. When the condition is met, <b>print</b> the number and <b>break</b> out of the loop.'
  },
  // { text: '<b>Hint:</b> Use <code>for n in range(1, 21):</code> — Inside, check <code>if n % 3 == 0 and n % 5 == 0:</code> — Then <code>print(n)</code> followed by <code>break</code> to stop the loop.', highlight: true },
]
</script>

<Slide
  topic="Loop Control"
  sub-topic="Practice Problem"
  :contents="contents"
/>
