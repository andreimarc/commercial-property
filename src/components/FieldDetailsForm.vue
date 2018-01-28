<template>
  <ul class="bc-DetailsForm__list">
    <li class="bc-DetailsForm__list-item">
      <label for="dlabel" class="bc-FormInput__label">Display Label</label>
      <input v-model="form.displayLabelModel" @blur="generateRefName(form.displayLabelModel)" class="bc-FormInput__input" type="text" name="dlabel" id="dlabel" required>
      <div class="bc-FormInput__subtext">For display purposes, spaces allowed</div>
    </li>
    <li class="bc-DetailsForm__list-item">
      <label for="refname" class="bc-FormInput__label">Reference Name</label>
      <input v-model="form.refNameModel" @blur="generateRefName(form.refNameModel)" class="bc-FormInput__input" type="text" name="refname" id="refname" required>
      <div class="bc-FormInput__subtext">Used to reference in calculations, no spaces allowed</div>
    </li>
    <li class="bc-DetailsForm__list-item">
      <label for="dvalue" class="bc-FormInput__label">Default Value</label>
      <input v-model="form.defaultValueModel" class="bc-FormInput__input" type="text" name="dvalue" id="dvalue">
    </li>
    <li class="bc-DetailsForm__list-item">
      <label for="customregex" class="bc-FormInput__label">Custom Validation</label>
      <select class="bc-FormInput__select" v-model="form.customValidationModel" name="customregex" id="customregex">
        <option disabled value="">Nothing selected</option>
        <option v-for="validator in customValidators" :key="validator.id">
          {{ validator.text }}
        </option>
      </select>
    </li>
  </ul>
</template>

<script>
// Field details inputs
export default {
  name: 'FieldDetailsForm',
  data () {
    return {
      // The data model. These items would normally be requested via AJAX,
      // but are hardcoded here for simplicity.
      form: {
        displayLabelModel: '',
        refNameModel: '',
        defaultValueModel: '',
        customValidationModel: ''
      },
      customValidators: [
        { value: 'alpha-numeric', text: 'Alpha-numeric' },
        { value: 'no-spaces', text: 'No spaces' },
        { value: 'phone-numbers', text: 'Phone numbers' }
      ]
    }
  },
  methods: {
    generateRefName: function (string) {
      let str = string.replace(/\s+/g, '-').toLowerCase()
      this.form.refNameModel = str
    }
  },
  components: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import '../assets/scss/form-input';

.bc-DetailsForm__list {
  padding: 0;
}

.bc-DetailsForm__list-item {
  float: left;
  margin-right: 2%;
  margin-bottom: 2%;
}
</style>
