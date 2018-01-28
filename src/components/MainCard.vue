<template>
  <form class="bc-FormElement" v-on:submit.prevent="preventSubmit('done!')">
    <div class="bc-LargeCard">
      <field-types></field-types>
      <field-details></field-details>
    </div>
    <form-actions></form-actions>
  </form>
</template>

<script>
import FieldTypes from './FieldTypes'
import FieldDetails from './FieldDetails'
import FormActions from './FormActions'

// Main page wrapper
export default {
  name: 'MainCard',
  components: {
    'field-types': FieldTypes,
    'field-details': FieldDetails,
    'form-actions': FormActions
  },
  methods: {
    preventSubmit: function (arg) {
      console.log(arg)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-LargeCard {
  background: #fff;
  display: flex;
  flex-direction: row;
  height: 100%;
  margin: 0 auto;
  width: 95%;
  border-radius: 10px;
  border: 1px solid rgba(0, 0, 0, .2);
  flex: 1 1 auto;
}

.bc-FormElement {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
}
</style>
