---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 15 — INDENTATION
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Syntax">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Indentation</span> Matters!</div>

<div class="card card-blue" style="margin-bottom:12px;" v-click>
  <div><strong>Python uses indentation instead of { } braces</strong> to define code blocks. Getting this wrong causes errors!</div>
</div>

<div class="g2" style="gap:14px;">

<div>
  <div class="slide-h3" style="color:#c73c3c;margin-bottom:6px;">Wrong — IndentationError!</div>

```python 
# Missing indentation — will CRASH!
if 5 > 2:
print("Five is greater")  # Error!
```

  <div v-click class="card card-red">
    IndentationError: expected an indented block
  </div>
</div>

<div>
  <div class="slide-h3" style="color:#38a169;margin-bottom:6px;">Correct — Uses 4 Spaces!</div>

```python {all}
# Proper indentation — works perfectly!
if 5 > 2:
    print("Five is greater")

# Nested indentation
for i in range(3):
    if i > 0:
        print(i)
```

  <div v-click class="card card-green">
    Five is greater<br>
    1<br>
    2
  </div>
</div>

</div>

<div v-after class="g2" style="gap:10px;margin-top:10px;">
<div class="card card-green">
  <div class="small-text">Use <strong>4 spaces</strong> per indentation level (PEP 8 standard)</div>
</div>
<div class="card card-red">
  <div class="small-text">Never mix <strong>tabs and spaces</strong> in the same file — causes TabError!</div>
</div>
</div>

  </template>
</Slide2>
