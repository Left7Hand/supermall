<template>
  <div class="tab-control">
    <div
      v-for="(item, index) in titles"
      :key="index"
      class="tab-control-item"
      :class="{ active: index === currentIndex }"
      @click="itemClick(index)"
    >
      <span>{{ item }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  data() {
    return {
      currentIndex: 0,
    };
  },
  props: {
    titles: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  methods: {
    itemClick(index) {
      this.currentIndex = index;
    },
  },
};
</script>

<style>
.tab-control {
  display: flex;
  text-align: center;
  font-size: 18px;
  height: 20px;
  line-height: 20px;
  background-color: #fff;
}

.tab-control-item {
  flex: 1;
}

.tab-control-item span {
  padding: 9px;
}

.active {
  color: var(--color-tint);
}

.active span {
  border-bottom: 3px solid var(--color-tint);
}
</style>