---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Given <code>s = "  Python Programming  "</code>, apply <code>strip()</code>, <code>upper()</code>, <code>replace("Python", "Java")</code>, <code>count("m")</code>, and <code>split()</code> — print each result.' },
  { text: '<b>Input:</b> <code>s = "  Python Programming  "</code>' },
  { text: '<b>Expected Output:</b> <code>strip() → "Python Programming"<br>upper() → "  PYTHON PROGRAMMING  "<br>replace("Python","Java") → "  Java Programming  "<br>count("m") → 2<br>split() → ["Python", "Programming"]</code>' },
  { text: '<b>Key Concepts:</b> Methods return new strings—the original string remains unchanged. Chain methods like <code>s.strip().lower()</code> for combined effects. <code>count()</code> is case-sensitive.' },
]
</script>

<Slide
  topic="Python Strings"
  sub-topic="String Methods — Test Yourself!"
  :contents="contents"
/>