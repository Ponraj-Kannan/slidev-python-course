---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take a student\'s name and marks as input. Use <code>if-elif-else</code> to determine the grade and <code>match-case</code> to determine the status. Print a formatted report card.' },
  { text: '<b>Input:</b><br><code>Enter student name: Priya</code><br><code>Enter marks (0-100): 85</code>' },
  {
    text: '<b>Expected Output:</b><br><code>--- Report Card ---</code><br><code>Name &nbsp;: Priya</code><br><code>Marks : 85</code><br><code>Grade : A — Distinction</code><br><br><b>Grade Ranges:</b><br><code>90 - 100 → A+ — Distinction</code><br><code>80 - 89 &nbsp;→ A &nbsp;— Distinction</code><br><code>70 - 79 &nbsp;→ B &nbsp;— Pass</code><br><code>50 - 69 &nbsp;→ C &nbsp;— Pass</code><br><code>0 &nbsp;- 49 &nbsp;→ F &nbsp;— Fail</code>'
  },
  {
    text: '<b>Key Concepts:</b> Use <code>if-elif-else</code> to assign a grade letter based on mark ranges — conditions must be checked <b>highest to lowest</b>. Then use <code>match grade:</code> with the <code>|</code> operator to group grades into a status — <code>case "A+" | "A":</code> for Distinction, <code>case "B" | "C":</code> for Pass, and <code>case _:</code> for Fail. Finally, use <b>f-strings</b> to print the formatted report card.'
  }
]
</script>

<Slide
  topic="Decision-making statements"
  sub-topic="Practice Problem"
  :contents="contents"
/>
