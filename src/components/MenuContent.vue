<template>
    <div v-for="i in props.popItem.items" :key="i.title" class="list-item">
        <div class="head">
            <img :src="'/src/Assets/' + i.icon + '.svg'" :alt="i.icon" />
            <span>{{ i.title }}</span>
        </div>
        <span class="detail">
            {{ i.detail }}
        </span>
    </div>
</template>
<script setup>
const props = defineProps(['popItem'])
</script>
<style scoped>
.head {
    display: flex;
    gap: 10px;
    font-size: 1rem;
    color: black;
    font-weight: 700;
    align-items: center;
}

.list-item {
    display: flex;
    flex-direction: column;
    gap: 5px;
    font-size: 0.9rem;
}

.detail {
    margin-left: 34px;
    font-size: 0.9rem;
}
</style>