<template>

<h1>Home</h1>

  <MyAcc :accordionContent="content"/>

</template>

<script>

import MyAcc from "@/components/MyAcc.vue"

export default {
  name: 'App',
  data () {
    return {
      content: [
        {title: "První Item", content: "První content itemu prvního", },
        {title: "Druhý Item", content: "Druhý content itemu druhého", },
        {title: "Třetí Item", content: "Třetí content itemu třetího", }
      ]
    }
  },
  components: { MyAcc }
}



</script>

<style>

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content:flex-start;
  height: 100vh;
  font-family: system-ui;
}

</style>