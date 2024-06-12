<template>
    <div class="header" @click="onClick">
        <div class="header-title">{{ item.title }}</div>
        <img :src="arrow" class="arrow" :class="{ closed: isOpen }" alt="arrow">
    </div>

    <transition name="slide-up">
        <div v-if="isOpen" class="content">{{ item.content }}</div>
    </transition>
</template>

<script>

import arrowImg from "@/assets/arrow.svg"

export default {
    name: 'MyAccItem',
    props: {
        item: Object,
        index: Number,
    },
    emits: ['opened', 'closed'],
    data() {
        return {
            opened: false,
        }
    },
    computed: {
        arrow() {
            return arrowImg;
        },
        isOpen() {
            return this.opened;
        }
    },
    methods: {
        onClick() {
            this.opened = !this.opened;
            this.$emit( this.opened ? 'opened' : 'closed', this.index);
        }
    }
}

</script>

<style scoped>

.header,
.content {
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

/* slide-up VUE translation */
.slide-up-enter-active {
    transition: all 0.6s ease;
}
.slide-up-leave-active {
    transition: all 0.4s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-up-enter,
.slide-up-leave-to {
    transform: translateY(-20px);
    opacity: 0;
}


.efect-enter-from,
.efect-leave-to {
    max-height: 0;
}

.efect-enter-to,
.efect-leave-from {
    max-height: 100%;
}

.efect-enter-active {
    transition: all .5s linear
}

.efect-leave-active {
    transition: all .5s linear
}
</style>