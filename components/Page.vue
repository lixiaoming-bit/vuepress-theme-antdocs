<template>
  <main class="page">
    <slot name="top" />

    <Content class="theme-antdocs-content" v-viewer />
    <PageEdit />

    <PageNav v-bind="{ sidebarItems }" />

    <slot name="bottom" />
  </main>
</template>

<script>
import PageEdit from '@theme/components/PageEdit.vue'
import PageNav from '@theme/components/PageNav.vue'

import 'viewerjs/dist/viewer.css'
import Viewer from 'v-viewer'
import Vue from 'vue'
Vue.use(Viewer)
export default {
  components: { PageEdit, PageNav },
  props: ['sidebarItems']
}
</script>

<style lang="less">
@import '../styles/palette.less';
@import "../styles/wrapper.less";
.page {
  padding-bottom: 2rem;
  display: block;
  img {
    cursor: zoom-in;
  }
}
@media (max-width: @MQMobile) {
  .page {
    margin-top: -@navbarHeight;
  }
}
</style>
