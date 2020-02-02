Mål | Teknik / Værktøj | Kriterier | Evaluering
----|------------------|-----------|-----------

{% assign table = site.data.tables | where: "name", include.tablename %}

<table>
  <tr>
    <th>Mål</th>
    <th>Teknik / Værktøj</th>
    <th>Kriterier</th>
    <th>Evaluering</th>
  </tr>
  {% for goal in table.goals %}
    {% for technique in goal.techniques %}
      <tr>
        <td>{{ goal.name }}</td>
        <td>
          {{ technique.name }}<br><br>
          {% for tool in technique.tools %}
          - {{ tool.line }}<br>
          {% endfor %}
        </td>
        <td>
          {% for criteria in technique.criterias %}
          {{ criteria.line }}<br><br>
          {% endfor %}
        </td>
        <td>
          {% for evaluation in technique.evaluations %}
          {{ evaluation.line }}<br><br>
          {% endfor %}
        </td>
      </tr>
    {% endfor %}
  {% endfor %}
</table>