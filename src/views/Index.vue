<template>
  <Main :aside="false">
    <Home />
    <Markdown :mark="mark" />
  </Main>
</template>

<style scoped>
.wrap {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>

<script setup>
import Main from '../components/Main.vue'
import Home from '../components/Home.vue'
import Markdown from '../components/Markdown.vue'
import { ref } from 'vue'
import axios from 'axios'


const mark = ref('')

axios({
  url: '/md/home.md'
}).then(res => {
  mark.value = res.data
})

</script>