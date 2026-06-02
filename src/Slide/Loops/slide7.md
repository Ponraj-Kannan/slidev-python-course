---
transition: slide-up
---

<script setup>
const contents = [
  { text: '<b>Problem:</b> Take a string as input and count the total number of <b>vowels</b> (<code>a, e, i, o, u</code>) in it. Print the count.' },
  { text: '<b>Input:</b> <code>hello world</code>' },
  {
    text: '<b>Expected Output:</b><br><code>Number of vowels: 3</code>'
  },
  // {
  //   text: '<b>Key Concepts:</b> Loop through each <b>character</b> in the string one by one using a <code>for</code> loop. Check if the character is a vowel by using the <code>in</code> operator against the string <code>"aeiou"</code>. Use a <b>counter variable</b> starting at <code>0</code> and increment it each time a vowel is found. Use <code>.lower()</code> to handle both uppercase and lowercase letters correctly.'
  // },
  // {
  //   text: '<b>Note:</b> Use <code>for ch in string:</code> to iterate over each character. Inside the loop, check <code>if ch.lower() in "aeiou":</code> and increment the counter. After the loop ends, print the final count.'
  // },
  // { text: '<b>Hint:</b> Start with <code>count = 0</code> — Use <code>for ch in text:</code> — Check <code>if ch.lower() in "aeiou":</code> then <code>count += 1</code> — Finally <code>print("Number of vowels:", count)</code>.', highlight: true },
]
</script>

<Slide
  topic="For Loop"
  sub-topic="String Iteration — Practice Problem"
  :contents="contents"
/>
