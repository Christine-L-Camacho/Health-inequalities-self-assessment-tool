<template>
  <h3 class="h3c">Health Inequalities Self-Assessment Tool</h3>
  <br>
  <p>
    This self-assessment tool is designed to be used alongside the Health Inequalities Objectives for NHS board members guide. The tool contains 25 questions across 4 domains:
  </p>

  <ul>
    <li>Building public health capacity and capability</li>
    <li>Data insight, evidence and evaluation</li>
    <li>Strategic leadership and accountability</li>
    <li>Systems partnerships</li>
  </ul>
  <p>
    When you are ready to start, click <a href="" @click.prevent="$emit('changePage', 'Section 1')">Section 1</a> and answer each question as either 'yes', 'no' or 'partial'. You may choose 'partial' instead of 'yes' if you have begun this work, e.g. with one staff group or as a one-off event, but it is not yet embedded in the Trust.
  </p>
  <p>
    The tool will provide a score and maturity rating for your Trust's position in each of these domains.
  </p>
  <br>
  <table>
    <tbody>
      <tr>
        <td>Percentage</td>
        <td>Maturity Rating</td>
      </tr>
      <tr>
        <td>0</td>
        <td>Not started</td>
      </tr>
      <tr>
        <td>1-24</td>
        <td>Emerging</td>
      </tr>
      <tr>
        <td>25-49</td>
        <td>Developing</td>
      </tr>
      <tr>
        <td>50-74</td>
        <td>Maturing</td>
      </tr>
      <tr>
        <td>75-100</td>
        <td>Thriving</td>
      </tr>
    </tbody>
  </table>
  <br>
  <p>
    When you have completed your answers, click on the 'Scores' button. The 'Reports' section gives bespoke suggestions for which health inequalities objectives your trust may wish to choose based on your responses.
  </p>
  
  <br>
  <div class="grid-filter__buttons">
        <button @click="$emit('changePage', 'Section 1')">Start Assessment</button>
  </div>
</template>

<script>
export default {
    name: 'InstructionsPage',
    emits: ['changePage'],
}
</script>

