---
transition: fade
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Use <b>multiple</b> <code>print()</code> statements to display your college name and current year on separate lines.' },
  {
    text: '<b>Expected Output:</b><br><code>I study at [Your College Name]</code><br><code>Year: [2024]</code>'
  },
  // {
  //   text: '<b>Key Concepts:</b> Each <code>print()</code> call automatically moves to a <b>new line</b> after printing. This means calling <code>print()</code> twice will produce two separate lines of output — no extra steps needed.'
  // },
  {
    text: '<b>Note:</b> Write <b>two separate</b> <code>print()</code> statements, one for your college name and one for the year. Replace <code>[Your College Name]</code> with your actual college name and <code>[2024]</code> with the current year. Each string must be wrapped in double quotes <code>" "</code>.'
  },
  // { text: '<b>Hint:</b> Type <code>print("I study at ABC College")</code> on the first line — Then <code>print("Year: 2024")</code> on the next line — Each print() moves to a new line automatically!', highlight: true },
]
</script>

<Slide
  topic="Getting Started with Python"
  sub-topic="Practice problem"
  :contents="contents"
/>
