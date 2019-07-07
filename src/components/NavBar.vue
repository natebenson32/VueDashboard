<template>
  <div class="navbar">
    <div class="collapse-btn" @click="$emit('sidebar')" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      sidebarOpen: true
    }
  }
}
</script>

<style lang="less">
.navbar {
  width: 100%;
  height: 60px;
  background: white;
  filter: drop-shadow(0 0 10px rgba(0, 0, 0, 0.3));
  display: flex;
}
.collapse-btn {
  width: 60px;
  background: url('../assets/hamburger.svg') center center no-repeat;
  background-size: 50%;
  cursor: pointer;
}
</style>
