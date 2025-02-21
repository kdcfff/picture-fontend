<template>
  <div id="globalHeader">
    <a-row>
      <a-col flex="100px">
        <router-link to="/">
          <div class="logo">
            <img src="../assets/logo.jpg" alt="logo">
          </div>
        </router-link>
      </a-col>
      <a-col flex="auto">
        <a-menu v-model:selectedKeys="current" mode="horizontal" :items="items" />
      </a-col>
      <a-col>
        <a-button type="primary">登录</a-button>
      </a-col>
    </a-row>
  </div>
</template>
<script lang="ts" setup>
import { h, ref } from 'vue'
import { HomeOutlined } from '@ant-design/icons-vue'
import { MenuProps } from 'ant-design-vue'

const current = ref<string[]>(['mail'])
const items = ref<MenuProps['items']>([
  {
    key: '/',
    icon: () => h(HomeOutlined),
    label: 'Navigation One',
    title: 'Navigation One'
  },
  {
    key: '/about',
    label: '关于',
    title: '关于'
  },
  {
    key: '/pay',
    label: '充值',
    title: '充值'
  }
])
</script>
<style scoped>
#globalHeader {
  align-items: center;
  background-color: #fff;
}

.logo {
  align-items: center;
  height: 100%;
}
</style>

