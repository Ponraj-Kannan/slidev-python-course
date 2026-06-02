---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Print a number triangle pattern using nested <b>for</b> loops.' },
  {
    text: '<b>Expected Output:</b><br><code>1</code><br><code>1 2</code><br><code>1 2 3</code><br><code>1 2 3 4</code>'
  },
  // {
  //   text: '<b>Pattern Logic:</b> The pattern has <b>4 rows</b>. Row 1 prints <code>1</code>, row 2 prints <code>1 2</code>, row 3 prints <code>1 2 3</code>, and row 4 prints <code>1 2 3 4</code>. Notice that row number <code>i</code> always prints numbers from <code>1</code> up to <code>i</code>.'
  // },
  // {
  //   text: '<b>Note:</b> Use an <b>outer loop</b> with <code>range(1, 5)</code> to control the <b>row number</b>. Use an <b>inner loop</b> with <code>range(1, i + 1)</code> to print numbers in each row. Use <code>end=" "</code> to print numbers on the same line, separated by spaces.'
  // },
  // { text: '<b>Hint:</b> Outer loop: <code>for i in range(1, 5):</code> — Inner loop: <code>for j in range(1, i + 1): print(j, end=" ")</code> — After the inner loop, add <code>print()</code> to move to the next line.', highlight: true },
]
</script>

<Slide
  topic="Nested Loops"
  sub-topic="Practice Problem"
  :contents="contents"
/>
