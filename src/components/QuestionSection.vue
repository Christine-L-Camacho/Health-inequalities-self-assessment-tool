<template>
  <h3 class="h3c">Health Inequalities Self-Assessment Tool</h3>
  <br>
  <table class="table--hide-side-lines table--hide-inner-vertical-lines">
    <tbody>
    <tr>
      <td colspan="3">{{ theme }}</td>
    </tr>
    <tr v-for="quest in questions" :key="quest.ref">
      <td>
        {{ quest.ref }}
      </td>
      <td>{{ quest.question }}</td>
      <td>
        <RadioButtonGroupComponent :sect=sect :q_num="quest.ref" :choice="existingScore(quest.ref)" @changeScore="$emit('changeScore', $event)"/>
      </td>
    </tr>
  </tbody>
  </table>
</template>

<script>
import RadioButtonGroupComponent from './RadioButtonGroupComponent.vue';

export default {
    name: 'QuestionSection',
    props: {
      sect: String,
      theme: String,
      questions: Array,
      existingselection: Object,
    },
    methods: {
    existingScore: function(q_num) {
      if (this.existingselection[q_num]) {
        return this.existingselection[q_num]
      }
      else {
        return null;
      }
    }
  },
    emits: ['changeScore'],
    components: { RadioButtonGroupComponent }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    padding: 20px;
}

.question {
    width: 75%;
}

.question-container {
    display: flex;
    align-items: left;
    justify-content: space-between;
    padding: 20px;
    margin-bottom: 10px;
    /* Add some space between question containers */
}

.radio-buttons {
    /* width: 25%; */
    display: flex;
    flex-direction: column;
    /* Set the direction to column to stack items vertically */
    align-items: flex-start;
    /* Align items to the right within the column */
    white-space: nowrap;
    /* Prevent label from wrapping to the next line */
}

input[type="radio"] {
    margin-right: 10px;
}

.table--hide-side-lines tbody tr td:first-child {
    border-left: 0
}

.table--hide-side-lines tbody tr td:last-child {
    border-right: 0
}

.table--hide-inner-vertical-lines tbody tr td {
    border-left-width: 0;
    border-right-width: 0
}

.table--hide-inner-vertical-lines tbody tr td:first-child {
    border-left-width: 1px
}

.table--hide-inner-vertical-lines tbody tr td:last-child {
    border-right-width: 1px
}
</style>
