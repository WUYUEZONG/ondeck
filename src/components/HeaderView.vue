<template>
    <div class="header-board">
        <div class="logo">
            <img src="/src/Assets/Logo.svg" alt="logo" />
        </div>
        <div class="menu-content">
            <div v-for="i in menuItems" :key="i.name" class="menu-item">
                <span>{{ i.name }}</span>
                <MenuPop v-if="i.items.length !== 0" :popItem="i" class="span-pop" />
            </div>
        </div>
        <div class="login-actions">
            <span>Sign in</span>
            <button class="button" @click="doSomething">Try for free</button>
        </div>
        <span class="expand-menu">
            <img src="/src/Assets/Menu.svg" alt="" @click="showMenus" />
            <MenuMinPop ref="minMenu" :menuItems="menuItems" />
        </span>
    </div>
</template>
<script setup>
import MenuMinPop from './MenuMinPop.vue';
import MenuPop from './MenuPop.vue';
import { ref } from 'vue';

const minMenu = ref(null)
const menuItems = [
    {
        name: 'Product',
        items: [
            {
                icon: 'Spense_Icon',
                title: 'Spense',
                detail: 'Spense is a landing page for writers. Great for practicing absolute positioning and fle layouts'
            },
            {
                icon: 'Fiber_Icon',
                title: 'Fiber Landing Page',
                detail: 'An online portfolio generator. Greate to practice flex/grid layouts, and absolute positioning.'
            },
            {
                icon: 'Gradie_Icon',
                title: 'Gradie Sign up Page',
                detail: 'Gradie is a simple sign up page, great to practice centering layouts.'
            },
        ]
    },
    {
        name: 'Challenges',
        items: []
    },
    {
        name: 'Resource',
        items: []
    },
    {
        name: 'Other Links',
        items: []
    },
]
function doSomething() {
    console.log('did')
}
function showMenus() {
    minMenu.value.show()
}

</script>

<style scoped>
.header-board {
    display: flex;
    justify-content: space-between;
    height: 100px;
    align-items: center;
}

.menu-item {
    position: relative;
}

.menu-content {
    display: flex;
    color: #999;
    font-size: 1.1rem;
    font-weight: 700;
    align-items: center;
    gap: 20px;
}

.span-pop {
    display: none;
    position: absolute;
    top: calc(100% + 20px);
    left: 50%;
    transform: translateX(-50%);
    z-index: 999;
}

.menu-content .menu-item>span:hover {
    color: #333;
    cursor: pointer;
}

.menu-content .menu-item>span:hover+.span-pop {
    display: flex;
}

.login-actions {
    display: flex;
    gap: 20px;
    align-items: center;
    font-size: 1.1rem;
}

.expand-menu {
    display: none;
}

@media (max-width: 767px) {

    .menu-content,
    .login-actions {
        display: none;
    }

    .expand-menu {
        display: block;
    }

    .header-board {
        height: 50px;
    }
}
</style>