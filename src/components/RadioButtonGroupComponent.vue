<template>
  <div class="radio-buttons">
    <label>
      <input type="radio" id="_yes" :name="sect + '.' + q_num" value="2" @click="$emit('changeScore', [q_num, 2])" :checked="checkThis(2)">
      Yes
    </label>
    <label>
      <input type="radio" id="_no" :name="sect + '.' + q_num" value="0" @click="$emit('changeScore', [q_num, 0])" :checked="checkThis(0)">
      No
    </label>
    <label>
      <input type="radio" id="_partial" :name="sect + '.' + q_num" value="1" @click="$emit('changeScore', [q_num, 1])" :checked="checkThis(1)">
      Partial
    </label>
  </div>
</template>

<script>
export default {
  name: 'RadioButtonGroupComponent',
  props: ['sect', 'q_num', 'choice'],
  emits: ['changeScore'],
  methods: {
    checkThis: function(item) {
      if (item === this.choice) {
        return true
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
</style>
