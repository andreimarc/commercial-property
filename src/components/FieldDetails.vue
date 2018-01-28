<template>
  <div class="bc-MainPanelContainer">
    <div class="bc-MainPanel">
      <div class="bc-MainForm">
        <bc-subheader :message="subheader"></bc-subheader>
        <field-details-form></field-details-form>
        <tags></tags>
      </div>
      <field-groups></field-groups>
    </div>
  </div>
</template>

<script>
// Middle part of the page, "Field Details" including the tags section
import Tags from './Tags'
import FieldGroups from './FieldGroups'
import Subheader from './Subheader'
import FieldDetailsForm from './FieldDetailsForm'

export default {
  name: 'FieldDetails',
  data () {
    return {
      // The data model. These items would normally be requested via AJAX,
      // but are hardcoded here for simplicity.
      subheader: 'Field Details'
    }
  },
  components: {
    'tags': Tags,
    'field-groups': FieldGroups,
    'bc-subheader': Subheader,
    'field-details-form': FieldDetailsForm
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-MainPanelContainer {
  flex: 1;
  position: relative;
}

.bc-MainPanel {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow-y: auto;
}

.bc-MainForm {
  width: 65%;
  float: left;
  padding: 0 20px;
}
</style>
