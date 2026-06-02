---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 29 — REAL-WORLD EXAMPLES
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Operators">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Real-World <span class="highlight">Examples</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">

  <div v-click class="section-label">Example 1 — Simple Interest Calculator</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#6b7280;"># SI = (P * R * T) / 100</span><br>
    <span style="color:#0e6ead;">principal</span> = <span style="color:#b45309;">10000</span><br>
    <span style="color:#0e6ead;">rate</span>      = <span style="color:#b45309;">8.5</span><br>
    <span style="color:#0e6ead;">time</span>      = <span style="color:#b45309;">3</span><br>
    <span style="color:#0e6ead;">si</span> = (<span style="color:#0e6ead;">principal</span> * <span style="color:#0e6ead;">rate</span> * <span style="color:#0e6ead;">time</span>) / <span style="color:#b45309;">100</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Interest: ₹{si}"</span>)  <span style="color:#6b7280;"># ₹2550.0</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Example 2 — Even or Odd Checker</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">num</span> = <span style="color:#b45309;">27</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">num</span> % <span style="color:#b45309;">2</span> == <span style="color:#b45309;">0</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Even"</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Odd"</span>)</span>
    <span style="color:#6b7280;"># Odd</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Example 3 — BMI Calculator</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">weight</span> = <span style="color:#b45309;">70</span>  <span style="color:#6b7280;"># kg</span><br>
    <span style="color:#0e6ead;">height</span> = <span style="color:#b45309;">1.75</span> <span style="color:#6b7280;"># m</span><br>
    <span style="color:#0e6ead;">bmi</span> = <span style="color:#0e6ead;">weight</span> / (<span style="color:#0e6ead;">height</span> ** <span style="color:#b45309;">2</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"BMI: {bmi:.2f}"</span>)  <span style="color:#6b7280;"># 22.86</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Example 4 — Login Validator</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">username</span> = <span style="color:#2d7a00;">"admin"</span><br>
    <span style="color:#0e6ead;">password</span> = <span style="color:#2d7a00;">"pass123"</span><br>
    <span style="color:#0e6ead;">correct_user</span> = <span style="color:#0e6ead;">username</span> == <span style="color:#2d7a00;">"admin"</span><br>
    <span style="color:#0e6ead;">correct_pass</span> = <span style="color:#0e6ead;">password</span> == <span style="color:#2d7a00;">"pass123"</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">correct_user</span> <span style="color:#ef5050;">and</span> <span style="color:#0e6ead;">correct_pass</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Access Granted ✓"</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Access Denied ✗"</span>)</span>
  </div>

  <div v-click class="section-label" style="margin-top:6px;">Example 5 — Grade Calculator</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">score</span> = <span style="color:#b45309;">85</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#0e6ead;">score</span> >= <span style="color:#b45309;">90</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Grade: A+"</span>)</span>
    <span style="color:#ef5050;">elif</span> <span style="color:#0e6ead;">score</span> >= <span style="color:#b45309;">80</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Grade: A"</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Grade: B"</span>)</span>
    <span style="color:#6b7280;"># Grade: A</span>
  </div>

  <div v-click class="callout callout-success" style="margin-top:6px;">
    <div>Operators are used in <strong>every real program</strong>. Mastering them means mastering Python logic!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
