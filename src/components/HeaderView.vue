<script setup>
</script>
<template>
    <div class="header-board">
        <div class="logo">
            <img src="/src/Assets/Logo.svg" alt="logo" />
        </div>
        <div class="menu-content">
            <span>Product</span>
            <span>Challenges</span>
            <span>Resources</span>
            <span>Other Links</span>
        </div>
        <div class="login-actions"> 
            <span>Sign in</span>
            <button class="button">Try for free</button>
        </div>
    </div>
</template>
<style scoped>
.header-board {
    display: flex;
    justify-content: space-between;
    height: 100px;
    align-items: center;
}
.menu-content {
    display: flex;
    gap: 20px;
    color: #999;
    font-size: 1.1rem;
    font-weight: 700;
}
.menu-content>span:hover {
    color: #333;
}

.login-actions {
    display: flex;
    gap: 20px;
    align-items: center;
    font-size: 1.1rem;
}

@media (max-width: 767px) {
    .menu-content, .login-actions {
        display: none;
    }
    .header-board {
        height: 50px;
    }
}

</style>