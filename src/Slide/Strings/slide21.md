
<Slide2 topic="Python Strings">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Real-World <span class="highlight">Examples</span> — User &amp; Email</div>

<div class="g2" style="gap:14px;align-items:start;">

<div class="flex-col">

  <div v-click class="section-label">Username Validator</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">username</span> = <span style="color:#ef5050;">input</span>(<span style="color:#2d7a00;">"Enter username: "</span>).strip()<br><br>
    <span style="color:#ef5050;">if</span> <span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">username</span>) < <span style="color:#b45309;">3</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Too short (min 3 chars)"</span>)</span>
    <span style="color:#ef5050;">elif</span> <span style="color:#2d7a00;">" "</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">username</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"No spaces allowed"</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Welcome, <span style="color:#ef5050;">{username.title()}</span>!"</span>)</span>
  </div>

  <div v-click class="section-label" style="margin-top:8px;">Password Strength Checker</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">pwd</span> = <span style="color:#ef5050;">input</span>(<span style="color:#2d7a00;">"Password: "</span>)<br>
    <span style="color:#0e6ead;">has_upper</span> = <span style="color:#ef5050;">any</span>(<span style="color:#0e6ead;">c</span>.isupper() <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">c</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">pwd</span>)<br>
    <span style="color:#0e6ead;">has_digit</span> = <span style="color:#ef5050;">any</span>(<span style="color:#0e6ead;">c</span>.isdigit() <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">c</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">pwd</span>)<br>
    <span style="color:#ef5050;">if</span> <span style="color:#ef5050;">len</span>(<span style="color:#0e6ead;">pwd</span>) >= <span style="color:#b45309;">8</span> <span style="color:#ef5050;">and</span> <span style="color:#0e6ead;">has_upper</span> <span style="color:#ef5050;">and</span> <span style="color:#0e6ead;">has_digit</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Strong password"</span>)</span>
    <span style="color:#ef5050;">else</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"Weak — add uppercase and digits"</span>)</span>
  </div>

</div>

<div class="flex-col">

  <div v-click class="section-label">Email Parser</div>
  <div v-after style="background:#f6f8fa;border-radius:10px;border:1px solid #e1e4e8;padding:12px 14px;font-family:'Fira Code',monospace;font-size:.72rem;line-height:1.9;">
    <span style="color:#0e6ead;">email</span> = <span style="color:#2d7a00;">"alice.smith@gmail.com"</span><br><br>
    <span style="color:#6b7280;"># Validate it's an email</span><br>
    <span style="color:#ef5050;">if</span> <span style="color:#2d7a00;">"@"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">email</span> <span style="color:#ef5050;">and</span> <span style="color:#0e6ead;">email</span>.endswith(<span style="color:#2d7a00;">".com"</span>):<br>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">at</span> = <span style="color:#0e6ead;">email</span>.find(<span style="color:#2d7a00;">"@"</span>)</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">user</span>   = <span style="color:#0e6ead;">email</span>[:<span style="color:#0e6ead;">at</span>]</span>
    <span style="padding-left:20px;display:block;"><span style="color:#0e6ead;">domain</span> = <span style="color:#0e6ead;">email</span>[<span style="color:#0e6ead;">at</span>+<span style="color:#b45309;">1</span>:]</span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"User: <span style="color:#ef5050;">{user}</span>"</span>)    <span style="color:#6b7280;"># alice.smith</span></span>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">f"Domain: <span style="color:#ef5050;">{domain}</span>"</span>) <span style="color:#6b7280;"># gmail.com</span></span>
  </div>

  <div v-click style="display:flex;flex-direction:column;gap:6px;margin-top:8px;">
    <div class="section-label">Skills Practised</div>
    <div style="display:flex;gap:6px;flex-wrap:wrap;">
      <span class="pill pill-red">len()</span>
      <span class="pill pill-blue">in / not in</span>
      <span class="pill pill-green">endswith()</span>
      <span class="pill pill-orange">find()</span>
      <span class="pill pill-navy">slicing</span>
      <span class="pill" style="background:#f0e6ff;color:#6b21a8;">f-strings</span>
    </div>
  </div>

  <div v-click class="callout callout-success" style="margin-top:8px; margin-bottom:40px">
    <div>These patterns appear in <strong>real login systems, sign-up forms, and contact validators</strong> used in production web applications every day!</div>
  </div>

</div>

</div>

  </template>
</Slide2>
