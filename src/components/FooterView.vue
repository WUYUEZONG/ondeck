<template>
    <div class="footer">
        <span>Trusted by 3+ million people at companies like</span>
        <div class="logos">
            <img src="@/Assets/NetflixLogo.svg" alt="" />
            <img src="@/Assets/ShopifyLogo.svg" alt="" />
            <img src="@/Assets/SpotifyLogo.svg" alt="" />
            <img src="@/Assets/WalmartLogo.svg" alt="" />
        </div>
    </div>
</template>
<style scoped>
.footer {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 40px;
    margin-top: 30px;
}
.logos {
    display: flex;
    gap: 40px;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;;
}

img {
    max-width: 46%;
}

@media (max-width: 767px) {
    .logos {
        gap: 20px;
    }
}

</style>