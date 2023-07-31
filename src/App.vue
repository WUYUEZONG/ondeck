<script setup>
import HeaderView from './components/HeaderView.vue';
import ContentView from './components/ContentView.vue'
import FooterView from './components/FooterView.vue'

</script>

<template>
  <div class="container">
    <header class="header">
      <HeaderView />
    </header>
    <main>
      <div class="center-content">
        <ContentView />
      </div>
    </main>
    <FooterView />
  </div>
</template>

<style>
body {
  /* display: flex;
  justify-content: center; */
  font-size: 1.1rem;
  background-color: var(--backgroundColor);
  color: var(--textColor);
}

#app {
  display: flex;
  justify-content: center;
}

.container {
  width: calc(100vw - 10%);
  max-width: 1200px;
  display: flex;
  flex-direction: column;
  gap: 100px;
}

.center-content {
  display: flex;
  gap: 80px;
  flex-wrap: wrap;
}


@media (max-width: 767px) {
    .container {
        gap: 40px;
    }
}

button {
  background-color: var(--buttonBgColor);
  padding: 12px 20px;
  border: 0;
  border-radius: 3px;
  font-size: 1.2rem;
  color: white;
}
</style>
