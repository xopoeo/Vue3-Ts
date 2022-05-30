<script  lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup

// 使用defineComponent()定义组件 可以让TS编译器检查组件的类型
import { defineComponent, onMounted, ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue';

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  setup: () => {
    const hello = ref<InstanceType<typeof HelloWorld> | null>(null)
    onMounted(() => {
      console.log(hello.value);
    })
    return { hello }
  }
})
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld ref="hello" msg="Hello Vue 3 + TS" :abc="123" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
