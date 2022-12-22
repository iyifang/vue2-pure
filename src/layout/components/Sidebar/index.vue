<template>
  <div class="sidebar-wrapper">
    <logo v-if="showLogo" />
    <el-scrollbar wrap-class="scrollbar-wrapper">
      <el-menu
        :default-active="activeMenu"
        :collapse="isCollapse"
        :background-color="variables.menuBg"
        :text-color="variables.menuText"
        :unique-opened="false"
        :active-text-color="variables.menuActiveText"
        :collapse-transition="false"
        mode="vertical"
      >
      </el-menu>
    </el-scrollbar>
  </div>
</template>

<script>
import Logo from "./Logo.vue";
import variables from '@/style/variables.scss'
import { mapGetters } from 'vuex'
export default {
  components: { Logo },
  computed: {
    ...mapGetters(["sidebar"]),
    showLogo() {
      return this.$store.state.settings.sidebarLogo;
    },
    activeMenu() {
      const route = this.$route;
      const { meta, path } = route;
      if (meta.activeMenu) {
        return meta.activeMenu;
      }
      return path;
    },
    isCollapse() {
      return !this.sidebar.opened;
    },
    variables(){
      return variables
    }
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang='scss' scoped>
</style>