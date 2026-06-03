<Slide2 topic="Tuple Operations">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Tuple <span class="highlight">Operations</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-red" style="text-align:center;">
    <div class="slide-h2" style="color:var(--red-dark);">Concatenation +</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">a</span> = (<span style="color:#b45309;">1</span>, <span style="color:#b45309;">2</span>)<br>
    <span style="color:#0e6ead;">b</span> = (<span style="color:#b45309;">3</span>, <span style="color:#b45309;">4</span>)<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">a</span> + <span style="color:#0e6ead;">b</span>)<br>
    <span style="color:#6b7280;"># (1, 2, 3, 4)</span>
  </div>

  <div v-click class="card card-orange" style="text-align:center;margin-top:4px;">
    <div class="slide-h2" style="color:var(--orange);">Repetition *</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">x</span> = (<span style="color:#b45309;">0</span>,) * <span style="color:#b45309;">5</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">x</span>)<br>
    <span style="color:#6b7280;"># (0, 0, 0, 0, 0)</span>
  </div>
</div>

<div class="flex-col">
  <div v-click class="card card-green" style="text-align:center;">
    <div class="slide-h2" style="color:var(--green);">Membership in / not in</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">t</span> = (<span style="color:#2d7a00;">"red"</span>, <span style="color:#2d7a00;">"green"</span>, <span style="color:#2d7a00;">"blue"</span>)<br>
    <br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"red"</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">t</span>)<br>
    <span style="color:#6b7280;"># True</span><br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#2d7a00;">"pink"</span> <span style="color:#ef5050;">not in</span> <span style="color:#0e6ead;">t</span>)<br>
    <span style="color:#6b7280;"># True</span>
  </div>

  <div v-click class="card card-blue" style="text-align:center;margin-top:4px;">
    <div class="slide-h2" style="color:var(--blue);">Looping</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#ef5050;">for</span> <span style="color:#0e6ead;">c</span> <span style="color:#ef5050;">in</span> <span style="color:#0e6ead;">t</span>:<br>
    <span style="padding-left:20px;display:block;"><span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">c</span>)</span>
  </div>
</div>

</div>

  </template>
</Slide2>
