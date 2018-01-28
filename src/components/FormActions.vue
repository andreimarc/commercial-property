<template>
  <div class="bc-formActionContainer">
    <bc-button :message="actionButtons[0].text" type="submit"></bc-button>
    <bc-button :message="actionButtons[2].text" :color="actionButtons[2].color" style="float: right; margin-left: 20px;"></bc-button>
    <bc-button :message="actionButtons[1].text" :color="actionButtons[1].color" style="float: right;"></bc-button>
  </div>
</template>

<script>
import Button from './Button'

// Form buttons at the bottom
export default {
  name: 'FormActions',
  data () {
    return {
      actionButtons: [
        {
          text: 'Save Changes',
          type: 'submit'
        },
        {
          text: 'Cancel Changes',
          color: 'white'
        },
        {
          text: 'Delete Input',
          color: 'red'
        }
      ]
    }
  },
  components: {
    'bc-button': Button
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-formActionContainer {
  margin: 20px auto;
  width: 95%;
  flex: 0 1 auto;
}
</style>
