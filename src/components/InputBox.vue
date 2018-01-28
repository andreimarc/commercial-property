<template>
  <button type="button" class="bc-SmallCard" v-on:click="selectOption()" v-bind:class="{ 'bc-SmallCard--active': isActive }">
    <div class="bc-SmallCard__title">
      <i class="material-icons">{{ message.icon }}</i>{{ message.title }}
    </div>
    <div class="bc-SmallCard__sublabel">Definition</div>
    <div class="bc-SmallCard__text">{{ message.definition }}</div>
    <div class="bc-SmallCard__sublabel">Default Display</div>
    <div class="bc-SmallCard__text">{{ message.default_display }}</div>
  </button>
</template>

<script>
// Input type card component on the left panel
export default {
  name: 'InputBox',
  props: ['message'],
  data () {
    return {
      isActive: false
    }
  },
  methods: {
    selectOption: function () {
      this.isActive = !this.isActive
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.bc-SmallCard {
  background: #fff;
  border: 1px solid #83a9af;
  border-radius: 5px;
  cursor: pointer;
  padding: 10px 13px;
  width: 260px;
  outline: 0;
  text-align: left;
  margin: 10px 0;
  transition: background .05s linear;

  &:hover {
    background: #eff4f5;
  }
}

.bc-SmallCard--active {
  background: #017c91;
  color: #fff;

  &:hover {
    background: #017c91;
  }

  .bc-SmallCard__sublabel {
    color: rgba(255, 255, 255, .7);
  }

  .bc-SmallCard__text {
    color: #fff;
  }
}

.bc-SmallCard__sublabel {
  color: #446268;
  display: block;
  font-size: 14px;
  margin-bottom: 5px;
}

.bc-SmallCard__text {
  color: #333;
  display: block;
  font-size: 16px;
  margin-bottom: 15px;
}

.bc-SmallCard__title {
  display: block;
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 20px;

  .material-icons {
    position: relative;
    top: 5px;
    margin-right: 5px;
  }
}
</style>
