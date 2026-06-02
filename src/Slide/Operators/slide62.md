---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 30 — PRACTICE PROGRAMS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Practice <span class="highlight">Programs</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="activity-box">
    <div class="act-title">🖊️ Program 1 — Arithmetic Explorer</div>
    <div class="act-task">
      Write a Python program that takes two numbers from the user and displays results for <strong>all 7 arithmetic operators</strong> (+, -, *, /, //, %, **).
    </div>
    <div class="hint">💡 Hint: Use <span class="mono">input()</span> + <span class="mono">int()</span> to read numbers from the user</div>
  </div>

  <div v-click class="activity-box" style="margin-top:6px;">
    <div class="act-title">🖊️ Program 2 — Leap Year Checker</div>
    <div class="act-task">
      A year is a leap year if: <strong>(divisible by 4 AND not divisible by 100) OR divisible by 400</strong>. Write a program that checks if a year is a leap year using logical operators.
    </div>
    <div class="hint">💡 Hint: Use <span class="mono">%</span> and <span class="mono">and</span>, <span class="mono">or</span>, <span class="mono">not</span></div>
  </div>

  <div v-click class="activity-box" style="margin-top:6px;">
    <div class="act-title">🖊️ Program 3 — Vowel Checker</div>
    <div class="act-task">
      Ask the user to enter a character and use the <strong>membership operator</strong> to check if it is a vowel (a, e, i, o, u).
    </div>
    <div class="hint">💡 Hint: <span class="mono">char in "aeiouAEIOU"</span></div>
  </div>

</div>

<div class="flex-col">

  <div v-click class="activity-box">
    <div class="act-title">🖊️ Program 4 — Compound Assignment Tracer</div>
    <div class="act-task">
      Start with <span class="mono">x = 50</span> and apply these steps in order using compound assignment operators: <strong>add 20, subtract 10, multiply by 3, floor-divide by 4, raise to power 2</strong>. Print value after each step.
    </div>
    <div class="hint">💡 Use +=, -=, *=, //=, **=</div>
  </div>

  <div v-click class="activity-box" style="margin-top:6px;">
    <div class="act-title">🖊️ Program 5 — Operator Precedence Quiz</div>
    <div class="act-task">
      Without running Python, predict the output of:<br>
      <strong>(a)</strong> <span class="mono">3 + 2 * 4 - 1</span><br>
      <strong>(b)</strong> <span class="mono">10 / 2 + 3 ** 2</span><br>
      <strong>(c)</strong> <span class="mono">5 > 3 and 2 < 4 or False</span>
    </div>
    <div class="hint">💡 Apply precedence rules, then verify with Python!</div>
  </div>

  <div v-click class="callout callout-warn" style="margin-top:6px;">
    <div><strong>Challenge:</strong> Write a single-line Python expression using at least 5 different operators that calculates the area of a circle: <span class="mono">A = π × r²</span></div>
  </div>

</div>

</div>

  </template>
</Slide2>
