---
transition: fade
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take an HTTP status code as input and use a <code>match</code> statement to print the correct status message. Handle multiple codes in a single <code>case</code> using the <code>|</code> operator.' },
  { text: '<b>Input:</b> <code>404</code>' },
  {
    text: '<b>Expected Output:</b><br><code>Not Found</code><br><br><b>More Test Cases:</b><br><code>200 or 201 → Success!</code><br><code>400 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→ Bad Request</code><br><code>500 or 503 → Server Error</code><br><code>999 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→ Unknown status</code>'
  }
]
</script>

<Slide
  topic="Match Case"
  sub-topic="Practice Problem"
  :contents="contents"
/>
