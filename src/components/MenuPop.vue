<template>
    <div class="popup">
        <MenuContent :popItem="props.popItem" />
    </div>
</template>
<script setup>
import MenuContent from './MenuContent.vue';

const props = defineProps(['popItem'])
</script>
<style scoped>
.popup {
    position: relative;
    display: flex;
    background-color: white;
    gap: 15px;
    border-radius: 4px;
    width: 300px;
    padding: 30px;
    flex-direction: column;
}
.popup:hover {
    display: flex;
}

.popup::after {
    content: "";
    position: absolute;
    top: -20px;
    left: 50%;
    transform: translateX(-50%);
    border-width: 10px;
    border-style: solid;
    border-color: transparent transparent white transparent;
}

</style>