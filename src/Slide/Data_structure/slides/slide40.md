<Slide2 topic="Collections — Detailed Comparison">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">All Four — <span class="highlight">Detailed</span> Comparison</div>

<table class="cmp-table">
  <thead>
    <tr>
      <th>Feature</th>
      <th>List</th>
      <th>Tuple</th>
      <th>Set</th>
      <th>Dictionary</th>
    </tr>
  </thead>
  <tbody>
    <tr v-click><td><strong>Ordered</strong></td><td class="yes">Yes</td><td class="yes">Yes</td><td class="no">No</td><td class="yes">Yes (3.7+)</td></tr>
    <tr v-click><td><strong>Mutable</strong></td><td class="yes">Yes</td><td class="no">No</td><td class="yes">Yes</td><td class="yes">Yes</td></tr>
    <tr v-click><td><strong>Duplicates allowed</strong></td><td class="yes">Yes</td><td class="yes">Yes</td><td class="no">No</td><td>Keys: No / Values: Yes</td></tr>
    <tr v-click><td><strong>Indexed</strong></td><td class="yes">Yes</td><td class="yes">Yes</td><td class="no">No</td><td>By Key</td></tr>
    <tr v-click><td><strong>Key-Value support</strong></td><td class="no">No</td><td class="no">No</td><td class="no">No</td><td class="yes">Yes</td></tr>
    <tr v-click><td><strong>Syntax</strong></td><td class="mono">[ ]</td><td class="mono">( )</td><td class="mono">{ }</td><td class="mono">{k: v}</td></tr>
    <tr v-click><td><strong>Speed (lookup)</strong></td><td>O(n)</td><td>O(n)</td><td class="yes">O(1)</td><td class="yes">O(1)</td></tr>
    <tr v-click><td><strong>Best for</strong></td><td>Ordered changing data</td><td>Fixed records</td><td>Unique items</td><td>Mapping</td></tr>
  </tbody>
</table>

  </template>
</Slide2>
