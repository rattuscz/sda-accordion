<template>

    <div class="container">

        <template v-for="(item, index) in accordionContent" :key="index">

            <div class="header" @click="$emit('clicked', index)">
                <div class="header-title">{{ item.title }}</div>
                <img :src="arrow" class="arrow" :class="{closed: isOpen}" alt="">
            </div>

            <transition name="efect">

                <div v-if="isOpen" class="content">{{ item.content }}</div>

            </transition>

        </template>

    </div>

</template>

<script>

import arrowImg from "@/assets/arrow.svg"

export default {

    name: 'MyAcc',
    props: {
        accordionContent: Array,
        isOpen: Boolean
    },
    data () {
        return {
            opened: false,
            arrow: arrowImg
        }
    }
}

</script>

<style scoped>

.container {
    display: flex;
    flex-direction: column;
    border: 1px solid #cdcdcd;
    border-radius: 5px;
    overflow: hidden;
    width: 100%;
    max-width: 400px;
}

.header, .content {
    padding: .7rem;
}

.header {
    display: flex;
    justify-content: space-between;
    cursor: pointer;
    background: #ededed;
    font-weight: bold;
}

.arrow {
    height: 1rem;
}

.closed {
    transform: rotateX(180deg);
    transition: all .3s linear
}

.efect-enter-from, .efect-leave-to {
    max-height: 0;
}

.efect-enter-to, .efect-leave-from {
    
    max-height: 100%;

}

.efect-enter-active{
    transition: all .5s linear
}

.efect-leave-active {
    animation: all .5s linear
}

</style>