---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take a temperature as input and print the appropriate weather advice based on the temperature range using <code>if-elif-else</code> conditions. If the input is outside the valid range, print an invalid data message.' },
  { text: '<b>Input:</b> <code>38</code>' },
  {
    text: '<b>Expected Output:</b><br><code>Very Hot! Stay hydrated</code><br><br><b>More Test Cases:</b><br><code>36 - 50 &nbsp;→ Very Hot! Stay hydrated</code><br><code>26 - 35 &nbsp;→ Warm and pleasant</code><br><code>16 - 25 &nbsp;→ Cool, carry a jacket</code><br><code>0 &nbsp;- 15 &nbsp;→ Very Cold!</code><br><code>-1 or 51+ → Invalid data!</code>'
  }
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>
