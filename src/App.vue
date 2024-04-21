<script setup lang="ts">
import SiderBar from './components/SiderBar.vue';


</script>

<template>
  <div class="app-container">
    <SiderBar></SiderBar>
    <div class="app-content">
      <router-view></router-view>
    </div>
  </div>

</template>

<style scoped>
.app-container {
  width: 100%;
  display: flex;
  gap: 2rem
}

.app-content {
  width: 100%;
  padding: 1rem;
  margin: 1rem 0;
  border-radius: 8px;
  background-color: #ffffff;
}
</style>
