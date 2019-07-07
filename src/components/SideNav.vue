<template>
  <div class="side-nav">
    <div class="static-bar" />
    <div class="flex-bar" />
  </div>
</template>

<script>
export default {}
</script>

<style>
.side-nav {
  height: 100%;
  display: flex;
}
.static-bar {
  width: 60px;
  background: rgb(18, 46, 82);
}
.flex-bar {
  flex: 1;
}
</style>
