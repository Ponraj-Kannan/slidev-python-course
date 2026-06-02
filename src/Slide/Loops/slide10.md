---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Print the multiplication table of 7 for numbers 1 through 10 using <code>range(1, 11)</code>.' },
  { text: '<b>Input:</b> No input required. The multiplier is fixed as <code>7</code> and the range is <code>1</code> to <code>10</code>.' },
  {
    text: '<b>Expected Output:</b><br><code>7 x 1 = 7</code><br><code>7 x 2 = 14</code><br><code>7 x 3 = 21</code><br><code>7 x 4 = 28</code><br><code>7 x 5 = 35</code><br><code>7 x 6 = 42</code><br><code>7 x 7 = 49</code><br><code>7 x 8 = 56</code><br><code>7 x 9 = 63</code><br><code>7 x 10 = 70</code>'
  },
  {
    text: '<b>Note:</b> Use a <b>for</b> loop with <code>range(1, 11)</code> to iterate from <code>1</code> to <code>10</code>. For each value of <code>i</code>, calculate <code>7 * i</code> and print it in the format <code>7 x i = result</code>.'
  },
  // { text: '<b>Hint:</b> Use <code>for i in range(1, 11):</code> and inside the loop print <code>f"7 x {i} = {7 * i}"</code> using an f-string.', highlight: true },
]
</script>

<Slide
  topic="For Loop"
  sub-topic="Practice Problem"
  :contents="contents"
/>
