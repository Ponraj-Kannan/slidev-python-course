---
transition: fade
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Write your very first Python program! Use the <code>print()</code> function to display your name on the screen.' },
  {
    text: '<b>Expected Output:</b><br><code>My name is [Your Name]</code>'
  },
  {
    text: '<b>Note:</b> Use the <code>print()</code> function and pass your name as a <b>string</b> inside double quotes <code>" "</code>. Replace <code>[Your Name]</code> with your actual name. A string is any text written inside quotes.'
  },
  // { text: '<b>Hint:</b> Type <code>print("My name is John")</code> — Replace <code>John</code> with your own name — Run the program and your name should appear on screen!', highlight: true },
]
</script>

<Slide
  topic="Getting Started with Python"
  sub-topic="Practice problem"
  :contents="contents"
/>
