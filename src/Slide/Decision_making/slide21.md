---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take a traffic signal color as input and use a <code>match</code> statement to print the correct action for each signal — <b>Stop</b>, <b>Slow down</b>, <b>Go</b>, or an <b>Unknown signal</b> message for anything else.' },
  { text: '<b>Input:</b> <code>green</code>' },
  {
    text: '<b>Expected Output:</b><br><code>Go!</code><br><br><b>More Test Cases:</b><br><code>red &nbsp;&nbsp;→ Stop!</code><br><code>yellow → Slow down!</code><br><code>blue &nbsp;→ Unknown signal!</code>'
  }
  // { text: '<b>Hint:</b> Start with <code>signal = input()</code> — Then <code>match signal:</code> — Add <code>case "red": print("🔴 Stop!")</code>, <code>case "yellow": print("🟡 Slow down!")</code>, <code>case "green": print("🟢 Go!")</code>, and <code>case _: print("❓ Unknown signal!")</code>', highlight: true },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>
