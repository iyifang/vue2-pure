<template>
  <div class="app-wrapper">
    <sidebar class="sidebar-container" />
  </div>
</template>

<script>
import { Sidebar } from "./components";
import ResizeMixin from "./mixin/ResizeHandler";
export default {
  mixins: [ResizeMixin],
  components: { Sidebar },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang='scss' scoped>
</style>