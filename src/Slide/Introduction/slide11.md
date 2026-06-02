---
transition: slide-up
---

<!-- ═══════════════════════════════════════════════════════
     SLIDE 16 — COMMENTS
═══════════════════════════════════════════════════════ -->

<Slide2 topic="Python Comments">
  <template #content>

<div class="slide-h1" style="margin-bottom:12px;"><span class="highlight">Comments</span></div>

<div class="body-text" style="margin-bottom:12px;">Comments are notes for humans — Python completely ignores them during execution.</div>

<div class="g2" style="gap:14px;align-items:start;">

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Single-line Comment <span class="mono" style="color:#ef5050;">#</span></div>

```python {1,2,4|all}
# This is a single-line comment
# Comments start with the # symbol

name = "Alice"   # inline comment too!
age  = 20        # this is her age
```

  <div v-click class="callout callout-info" style="margin-top:8px;">
    <div>Use <span class="mono">#</span> for short explanations on a single line.</div>
  </div>
</div>

<div>
  <div class="slide-h3" style="margin-bottom:6px;">Multi-line Comment <span class="mono" style="color:#ef5050;">"""..."""</span></div>

```python {1,2,3,4,5|all}
"""
This is a multi-line comment.
Also called a docstring.
Used to document functions & modules.
"""

def greet():
    """This function prints a greeting."""
    print("Hello!")
```

  <div v-click class="callout callout-warn" style="margin-top:8px;">
    <div>Triple quotes <span class="mono">"""</span> are technically <strong>strings</strong>, but used as multiline comments when not assigned.</div>
  </div>
</div>

</div>

<div v-click class="callout callout-success" style="margin-top:10px;">
  <div><strong>Best practice:</strong> Write comments that explain <em>WHY</em> you wrote the code, not just <em>WHAT</em> it does. Good code is self-explanatory!</div>
</div>

  </template>
</Slide2>
