---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Create variables for a student profile: <code>name</code> (string), <code>age</code> (int), <code>gpa</code> (float), <code>is_enrolled</code> (bool). Print each variable and its type using <code>type()</code>.' },
  { text: '<b>Expected Output:</b><br><code>Alice &lt;class \'str\'&gt;</code><br><code>20 &lt;class \'int\'&gt;</code><br><code>9.2 &lt;class \'float\'&gt;</code><br><code>True &lt;class \'bool\'&gt;</code>' },
  { text: '<b>Note:</b> Use <code>print(variable, type(variable))</code> to print the value and type together on one line.' },
]
</script>

<Slide
  topic="Type Checking & Conversion"
  sub-topic="Practice Problem"
  :contents="contents"
/>
