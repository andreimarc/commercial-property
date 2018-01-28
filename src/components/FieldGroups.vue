<template>
  <div class="bc-RightPanel">
    <bc-subheader :message="subheader" style="font-size: 16px;"></bc-subheader>
    <p>Choose a group for this input</p>
    <ul class="bc-RightPanel__list">
      <li class="" v-for="group in field_groups" :key="group.id">
        <field-group-button v-bind:group="group"></field-group-button>
      </li>
    </ul>
    <bc-button :message="button_label" color="white" v-on:click.native="addNewGroup()" style="width: 100%;"></bc-button>
  </div>
</template>

<script>
import FieldGroupButton from './FieldGroupButton'
import Subheader from './Subheader'
import Button from './Button'

// The colored field groups component on the right side
export default {
  name: 'FieldGroups',
  data () {
    return {
      field_groups: [
        {
          'title': 'Rental Vehicle Coverage Package',
          'total_inputs': 7
        }
      ],
      new_group: {
        'title': 'New field group',
        'total_inputs': 0
      },
      subheader: 'Field Groups',
      button_label: 'Add A New Group'
    }
  },
  props: [],
  components: {
    'field-group-button': FieldGroupButton,
    'bc-subheader': Subheader,
    'bc-button': Button
  },
  methods: {
    addNewGroup: function () {
      this.field_groups.push(this.new_group)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-RightPanel {
  background: #f9fbfb;
  border: 1px solid rgba(131, 169, 175, .3);
  border-radius: 5px;
  float: left;
  height: auto;
  min-height: 400px;
  width: 230px;
  margin: 25px 10px;
  text-align: left;
  padding: 10px;
}

.bc-RightPanel__list {
  padding: 0;
}
</style>
