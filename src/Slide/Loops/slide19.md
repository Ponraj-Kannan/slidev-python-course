---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Display the following star pattern using a nested loop.' },
  {
    label: 'Expected Output',
    text: '*\n* *\n* * *\n* * * *\n* * * * *',
    codeEditor: true,
    lang: 'java',
  },
  { text: '<b>Note:</b> Use a nested <b>for</b> loop. Row 1 has 1 star, row 2 has 2 stars, and so on up to 5 rows.' },
  // { text: '<b>Hint:</b> The outer loop runs from <code>i = 1</code> to <code>5</code>. The inner loop runs from <code>j = 1</code> to <code>i</code>. Print <code>"* "</code> inside the inner loop and call <code>System.out.println()</code> after it.', highlight: true },
]
</script>

<Slide
  topic="Loop Control"
  sub-topic="Practice Problem"
/>
