<template>
  <button type="button" class="bc-GroupCard" v-on:click="selectFieldGroup()" v-bind:class="{ 'bc-GroupCard--active': isActive }">
    <div class="bc-GroupCard__title">{{ group.title }}</div>
    <div>{{ group.total_inputs}} other inputs</div>
  </button>
</template>

<script>
// Selectable field group card component
export default {
  name: 'FieldGroupButton',
  data () {
    return {
      isActive: false
    }
  },
  props: ['group'],
  components: {
  },
  methods: {
    selectFieldGroup: function () {
      this.isActive = !this.isActive
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-GroupCard {
  background: #fff;
  border: 1px solid #83a9af;
  border-radius: 5px;
  padding: 10px 13px;
  width: 100%;
  outline: 0;
  text-align: left;
  margin-bottom: 20px;
  transition: background .05s linear;
}

.bc-GroupCard--active {
  background: #017c91;
  color: #fff;
}

.bc-GroupCard__title {
  font-size: 13px;
  font-weight: bold;
  margin-bottom: 5px;
}
</style>
