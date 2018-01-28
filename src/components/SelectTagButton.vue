<template>
  <button class="bc-Tags__btn" type="button" v-on:click="selectTag()" v-bind:class="{ 'bc-Tags__btn--active': isActive }">{{ tag }}</button>
</template>

<script>
// Tag selector component
export default {
  name: 'SelectTagButton',
  data () {
    return {
      isActive: false
    }
  },
  props: ['tag'],
  methods: {
    selectTag: function () {
      this.isActive = !this.isActive
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-Tags__btn {
  background: #eff4f5;
  border: 1px solid rgba(131, 169, 175, .3);
  border-radius: 3px;
  color: #017c91;
  cursor: pointer;
  font-weight: bold;
  margin-right: 5px;
  outline: 0;

  &:hover {
    background: #c6d9dd;
  }
}

.bc-Tags__btn--active {
  background: #017c91;
  color: #eff4f5;

  &:hover {
    background: #017c91;
    color: #eff4f5;
  }
}
</style>
