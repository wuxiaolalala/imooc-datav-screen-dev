<template>
  <div class="country-category">
    <div class="category" v-for="(item) in data" :key="item">
      <div>{{item}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TransformCategory',
  props: {
    data: Array,
    color: {
      type: Array,
      default() {
        return ['rgb(140, 160, 173)', 'rgb(80, 80, 80)']
      }
    }
  },
  setup(props) {
  }
}
</script>

<style lang="scss" scoped>
.country-category {
  display: flex;
  width: 100%;
  height: 100%;

  .category {
    flex: 1;
    background: rgb(53, 57, 65);
    font-size: 24px;
    color: rgb(144, 160, 174);

    .hovered {
      background: rgb(80, 80, 80);
    }

    .selected {
      background: rgb(140, 160, 173);
      color: #fff;
    }

    div {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
    }
  }
}
</style>
