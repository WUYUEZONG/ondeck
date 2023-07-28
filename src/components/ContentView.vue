<script setup>
const icons = ['CapterraLogo', 'AlternativeToLogo']
</script>
<template>
    <div class="content">
        <div class="content-main">
            <div>
                <span class="title dark">Ondeck is your remote </span>
                <span class="title light">conference calling tool</span>
            </div>
            <div>
                Ondeck is a service that allows you to create beautiful, online, and encrypted video calls for you and your
                remote team.
            </div>
            <button>Try for free</button>
            <div class="content-footer">
                <span>5.0 Rating based on reviews from:</span>
                <img v-for='icon in icons' :key="icon" :src="'@/Assets/' + icon + '.svg'" :alt="icon" />
            </div>
        </div>
        <img class="info-img" src="@/Assets/HeroImage.png" alt="" />
    </div>
</template>
<style scoped>
.content {
    display: flex;
    gap: 80px;
    font-size: 1.1rem;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
}

.content-main {
    display: flex;
    flex-direction: column;
    gap: 30px;
    align-items: flex-start;
    min-width: 340px;
    flex: 1;
}

.content-footer {
    display: flex;
    gap: 20px;
    align-items: center;
}

.title {
    font-size: 5rem;
}

.dark {
    color: black;
}

.light {
    color: var(--yellow);
}

.info-img {
    width: 340px;
    height: auto;
}

@media (max-width: 767px) {
    .title {
        font-size: 2.9rem;
    }

    .content-footer {
        gap: 10px;
    }

    .content-footer img {
        width: 20px;
    }

    .info-img {
        display: none;
    }
}</style>