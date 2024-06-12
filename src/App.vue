<template>

<h1>Home</h1>

  <MyAccSingle :accordionContent="content" />
  
  <hr />

  <MyAccMulti :accordionContent="content" />

</template>

<script>

import MyAccSingle from "@/components/MyAccSingle.vue"
import MyAccMulti from "@/components/MyAccMulti.vue"

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
  components: { MyAccSingle, MyAccMulti }
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

hr {
  width: 100%;
}

</style>