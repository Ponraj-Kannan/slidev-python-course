---
transition: slide-up
---

<script setup>
const contents = [
  { text: 'Assign a grade to a student based on their marks.' },
  { text: 'Mark &gt;= 90 → Print <b>A</b>' },
  { text: 'Mark &gt;= 80 → Print <b>B</b>' },
  { text: 'Mark &gt;= 70 → Print <b>C</b>' },
  { text: 'Mark &gt;= 60 → Print <b>D</b>' },
  { text: 'Else → Print <b>F</b>' },
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>
