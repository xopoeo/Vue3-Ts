<script  lang="ts">
import { ref, defineComponent, PropType, onMounted } from 'vue'

interface User {
  msg: string
  abc: number
}

export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      required: true
    },
    abc: {
      type: Number,
      required: true
    },
    Obj: {
      type: Object as PropType<User>,
    }
  },
  setup(props) {
    const msg = ref(props.msg)
    console.log(msg.value);
    const Font = ref<{ msg: String, abc: Number } | null>(null)
    Font.value = {
      msg: "vue3",
      abc: 123
    }
    const title = ref<HTMLHeadElement | null>(null)
    onMounted(() => {
      console.log(title.value);
    })
    // 方法
    const say = () => {
      console.log("say");
    }
    return { title }
  }
})
</script>

<template>
  <h1 ref="title">{{ msg }}</h1>

  <p>
    Recommended IDE setup:
    <a href="https://code.visualstudio.com/" target="_blank">VS Code</a>
    +
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
  </p>

  <p>See <code>README.md</code> for more information.</p>


</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
