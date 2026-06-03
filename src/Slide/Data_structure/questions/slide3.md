<script setup>
const contents = [
  { text: '<b>Problem:</b> You are given a list that contains duplicate values. Write a Python program to remove all duplicates and print the unique list. Also count how many times each duplicate element appeared.' },
  { text: '<b>Input 1:</b> <code>[1, 2, 2, 3, 3, 3, 4]</code>' },
  { text: '<b>Input 2:</b> <code>[5, 5, 6, 7, 7, 7, 7]</code>' },
  { text: '<b>Expected Output:</b> <code>Unique list : [1, 2, 3, 4]</code><br><code>Duplicate counts : {2: 2, 3: 3}</code><br><code>Unique list : [5, 6, 7]</code><br><code>Duplicate counts : {5: 2, 7: 4}</code>' }
]
</script>
<Slide
  topic="Python Lists"
  sub-topic="Practice Problem 3"
  :contents="contents"
/>
