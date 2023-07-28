<template>
    <div v-show="isShow" class="container" @click="hideSelf">
        <div class="popup">
        <div v-for="i in menuItems" :key="i.name" class="item">
            <span>{{ i.name }}</span>
            <MenuContent :popItem="i" />
        </div>
        <span class="close" @click="hideSelf">
            <img src="/src/Assets/Close.svg" alt="" />
        </span>
    </div>
    </div>
</template>

<script setup>
import MenuContent from './MenuContent.vue';
import { watchEffect, ref } from 'vue';

defineProps(['menuItems'])
const isShow = ref(false)

watchEffect(() => {
    function handleResize() {
        if (window.innerWidth > 767) {
            isShow.value = false
        }
    }
    window.addEventListener('resize', handleResize)
    return () => {
        window.removeEventListener('resize', handleResize)
    }
})

const show = () => {
    isShow.value = true
}
const hideSelf = () => {
    isShow.value = false
}
defineExpose({
    show
})

</script>

<style scoped>

.container {
    position: fixed;
    top: 0;
    bottom: 0;
    right: 10px;
    /* background-color: rgba(0, 0, 0, 0.3); */
    display: flex;
    align-items: flex-end;
    padding-top: 10px;
}
.popup {
    display: flex;
    flex-direction: column;
    background-color: white;
    gap: 15px;
    border-radius: 4px;
    width: 280px;
    padding: 30px;
    z-index: 99;
    position: relative;
    max-height: 60%;
    overflow-y: auto;
}

.item {
    display: flex;
    flex-direction: column;
    gap: 15px;
}
.close {
    position: absolute;
    top: 20px;
    right: 20px;
}
</style>