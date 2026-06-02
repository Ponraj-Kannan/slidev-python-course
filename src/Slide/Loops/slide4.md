---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Print all odd numbers from 1 to 20 using a while loop.' },
  { text: '<b>Input:</b> No input required. The range is fixed from <code>1</code> to <code>20</code>.' },
  {
    text: '<b>Expected Output:</b><br><code>1</code><br><code>3</code><br><code>5</code><br><code>7</code><br><code>9</code><br><code>11</code><br><code>13</code><br><code>15</code><br><code>17</code><br><code>19</code>'
  },
  // {
  //   text: '<b>Note:</b> Use a <b>while</b> loop starting from <code>1</code>. Print the number if it is odd, then increment by <code>1</code> each iteration. The loop should run as long as the number is less than or equal to <code>20</code>.'
  // },
  // { text: '<b>Hint:</b> Use <code>while (n <= 20)</code>. Inside the loop, check <code>if (n % 2 !== 0)</code> to identify odd numbers, then print <code>n</code> and increment with <code>n++</code>.', highlight: true },
]
</script>

<Slide
  topic="While Loop"
  sub-topic="Practice Problem"
  :contents="contents"
/>
