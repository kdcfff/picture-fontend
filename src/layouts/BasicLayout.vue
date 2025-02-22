<script setup lang="ts">

import GlobalHeader from '@/components/GlobalHeader.vue'
</script>

<template>
  <div id="basicLayout">
    <a-layout style="min-height: 100vh">
      <a-layout-header class="header">
        <GlobalHeader />
      </a-layout-header>
      <a-layout-content class="content">
        <router-view />
      </a-layout-content>
      <a-layout-footer class="footer">
        <a href="https://github.com/vuejs/theme" target="_blank">vuejs</a>
      </a-layout-footer>
    </a-layout>
  </div>
</template>

<style scoped>
#basicLayout .header {
  padding-inline: 10px;
  background: white;
  color: unset;
}

#basicLayout .footer {
  background: #efefef;
  padding: 20px;
  font-size: large;
  text-align: center;
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
}

#basicLayout .content {
  padding: 20px 20px 20px 40px;
  background: linear-gradient(to right, #fefefe, #fff);
  margin-bottom: 50px;
}
</style>
