<Slide2 topic="Quick Comparison Preview">
  <template #content>

<div class="slide-h1" style="margin-bottom:10px;">Quick <span class="highlight">Comparison</span> Preview</div>

<table class="cmp-table">
  <thead>
    <tr>
      <th>Property</th>
      <th>List</th>
      <th>Tuple</th>
      <th>Set</th>
      <th>Dictionary</th>
    </tr>
  </thead>
  <tbody>
    <tr v-click>
      <td><strong>Syntax</strong></td>
      <td class="mono">[1, 2, 3]</td>
      <td class="mono">(1, 2, 3)</td>
      <td class="mono">{1, 2, 3}</td>
      <td class="mono">{"a": 1}</td>
    </tr>
    <tr v-click>
      <td><strong>Ordered</strong></td>
      <td class="yes">Yes</td>
      <td class="yes">Yes</td>
      <td class="no">No</td>
      <td class="yes">Yes (3.7+)</td>
    </tr>
    <tr v-click>
      <td><strong>Mutable</strong></td>
      <td class="yes">Yes</td>
      <td class="no">No</td>
      <td class="yes">Yes</td>
      <td class="yes">Yes</td>
    </tr>
    <tr v-click>
      <td><strong>Duplicates allowed</strong></td>
      <td class="yes">Yes</td>
      <td class="yes">Yes</td>
      <td class="no">No</td>
      <td>Keys: No / Values: Yes</td>
    </tr>
    <tr v-click>
      <td><strong>Index access</strong></td>
      <td class="yes">Yes</td>
      <td class="yes">Yes</td>
      <td class="no">No</td>
      <td>By Key</td>
    </tr>
    <tr v-click>
      <td><strong>Typical use</strong></td>
      <td>Ordered changing data</td>
      <td>Fixed records</td>
      <td>Unique items</td>
      <td>Name -> value lookups</td>
    </tr>
  </tbody>
</table>

<div v-click class="callout callout-info" style="margin-top:12px;">
  <div><strong>Coming up:</strong> we'll dive into each collection — features, creation, methods, real examples, and coding practice.</div>
</div>

  </template>
</Slide2>
