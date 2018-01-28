<template>
  <div class="bc-LeftPanel">
    <bc-subheader :message="subheader"></bc-subheader>
    <label for="filter-input" class="bc-FormInput__label">Filter Types</label>
    <input type="text" class="bc-FormInput__input" id="filter-input" name="filter-input" v-model="searchString" />
    <ul class="bc-TypesList">
      <!-- Render a li element for every entry in the computed filteredArticles array. -->
      <li v-for="filteredInput in filteredInputs" :key="filteredInput.id">
        <input-box v-bind:message="filteredInput"></input-box>
      </li>
    </ul>
  </div>
</template>

<script>
import InputBox from './InputBox'
import Subheader from './Subheader'

// Filtering widget on the left side of the page
export default {
  name: 'FieldTypes',
  data () {
    return {
      subheader: 'Field Types',
      searchString: '',
      // The data model. These items would normally be requested via AJAX,
      // but are hardcoded here for simplicity.
      inputTypes: [
        {
          'title': 'Text',
          'definition': 'String of text',
          'default_display': 'Free form text input',
          'icon': 'text_format'
        },
        {
          'title': 'Date',
          'definition': 'Standard ISO format date',
          'default_display': 'Datepicker, with configurable format',
          'icon': 'date_range'
        },
        {
          'title': 'VIN',
          'definition': 'Vehicle identification number',
          'default_display': 'Free form text input',
          'icon': 'card_travel'
        }
      ],
      msg: 'filter card'
    }
  },
  components: {
    'input-box': InputBox,
    'bc-subheader': Subheader
  },
  computed: {
    // A computed property that holds only those articles that match the searchString.
    filteredInputs: function () {
      let inputsArray = this.inputTypes
      let searchString = this.searchString

      if (!searchString) {
        return inputsArray
      }

      searchString = searchString.trim().toLowerCase()

      inputsArray = inputsArray.filter(function (item) {
        if (item.title.toLowerCase().indexOf(searchString) !== -1) {
          return item
        }
      })

      // Return an array with the filtered data.
      return inputsArray
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import '../assets/scss/form-input';

.bc-LeftPanel {
  background: #eff4f5;
  border-radius: 10px 0 0 10px;
  box-shadow: 0 0 1px 0 #017c91 inset;
  overflow-y: auto;
  width: 260px;
  padding: 0 20px;
}

.bc-TypesList {
  margin: 0;
  padding: 0;
}
</style>
