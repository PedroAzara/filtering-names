<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p >You are searching for: {{search}}</p>
    <div v-for="name in matchingNames" :key="name">{{name}}</div>
  </div>
</template>

<script>

import {ref, computed} from 'vue'
export default {
  name: 'Home',
  setup(){
    const search = ref('')
    const names = ref(['pedro', 'mario', 'shaun', 'maran', 'sauan', 'saron'])

  

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))

    })

      return {names, search, matchingNames}
  }
}
</script>
