<template>

<h1>Home</h1>

  <MyAcc :accordionContent="content" @clicked="onClick" :isOpen="isOpened"/>

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
      ],
      isOpened: true
    }
  },
  methods: {
    onClick (index) {
      console.log(this.content[index].title + index)
      this.isOpened = !this.isOpened
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