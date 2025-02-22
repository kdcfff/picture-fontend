<template>
  <div id="globalHeader">
    <a-row :wrap="false">
      <a-col flex="200px">
        <router-link to="/">
          <div class="logo">
            <img src="../assets/logo.jpg" alt="logo">
            <div class="title">
              Vue3
            </div>
          </div>
        </router-link>
      </a-col>
      <a-col flex="auto">
        <a-menu v-model:selectedKeys="current" mode="horizontal" :items="items" @click="doMenuClick" />
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
import { useRouter } from 'vue-router'

const router = useRouter()
const doMenuClick = ({ key }) => {
  router.push({
    path: key,
  })
}
// 监听路由变化让菜单高亮
const current = ref<string[]>([])
// 监听路由变化让菜单高亮
router.afterEach((to , from , next) => {
  current.value = [to.path]
})

const items = ref<MenuProps['items']>([
  {
    key: '/',
    icon: () => h(HomeOutlined),
    label: '主页',
    title: '主页'
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
  background-color: #fff;
}

.logo {
  display: flex;
  align-items: center;
  height: 100%;
}

.title {
  color: black;
  font-size: 18px;
  margin-left: 10px;
}
</style>

