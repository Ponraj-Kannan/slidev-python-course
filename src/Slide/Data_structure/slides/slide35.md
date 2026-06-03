<Slide2 topic="Add, Update &amp; Remove Entries">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;"><span class="highlight">Add</span>, <span class="highlight">Update</span> &amp; <span class="highlight">Remove</span></div>

<div class="g2" style="gap:14px;">

<div class="flex-col">
  <div v-click class="card card-blue" style="text-align:center;">
    <div class="slide-h2" style="color:var(--blue);">Add &amp; Update</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">d</span> = {<span style="color:#2d7a00;">"name"</span>: <span style="color:#2d7a00;">"Anu"</span>}<br>
    <br>
    <span style="color:#6b7280;"># Add a new key</span><br>
    <span style="color:#0e6ead;">d</span>[<span style="color:#2d7a00;">"age"</span>] = <span style="color:#b45309;">19</span><br>
    <br>
    <span style="color:#6b7280;"># Update existing key</span><br>
    <span style="color:#0e6ead;">d</span>[<span style="color:#2d7a00;">"name"</span>] = <span style="color:#2d7a00;">"Anita"</span><br>
    <br>
    <span style="color:#6b7280;"># Bulk update</span><br>
    <span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">update</span>({<span style="color:#2d7a00;">"city"</span>: <span style="color:#2d7a00;">"Chennai"</span>})<br>
    <span style="color:#2d7a00;">print</span>(<span style="color:#0e6ead;">d</span>)
  </div>

  <div v-click class="output-box">{'name': 'Anita', 'age': 19, 'city': 'Chennai'}</div>
</div>

<div class="flex-col">
  <div v-click class="card card-red" style="text-align:center;">
    <div class="slide-h2" style="color:var(--red-dark);">Remove</div>
  </div>

  <div v-click class="code-block">
    <span style="color:#0e6ead;">d</span> = {<span style="color:#2d7a00;">"a"</span>: <span style="color:#b45309;">1</span>, <span style="color:#2d7a00;">"b"</span>: <span style="color:#b45309;">2</span>, <span style="color:#2d7a00;">"c"</span>: <span style="color:#b45309;">3</span>}<br>
    <br>
    <span style="color:#6b7280;"># by key</span><br>
    <span style="color:#0e6ead;">x</span> = <span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">pop</span>(<span style="color:#2d7a00;">"a"</span>)<br>
    <span style="color:#6b7280;"># x=1, d={'b':2,'c':3}</span><br>
    <br>
    <span style="color:#6b7280;"># last inserted pair</span><br>
    <span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">popitem</span>()<br>
    <br>
    <span style="color:#6b7280;"># delete a specific key</span><br>
    <span style="color:#ef5050;">del</span> <span style="color:#0e6ead;">d</span>[<span style="color:#2d7a00;">"b"</span>]<br>
    <br>
    <span style="color:#6b7280;"># wipe everything</span><br>
    <span style="color:#0e6ead;">d</span>.<span style="color:#0e6ead;">clear</span>()
  </div>
</div>

</div>

  </template>
</Slide2>
