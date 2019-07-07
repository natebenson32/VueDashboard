<template>
  <div class="side-nav">
    <div class="static-bar">
      <div class="menu-btn" v-for="(item, index) in sideButtons" :key="index">
        <div class="menu-icon"></div>
      </div>
    </div>
    <div class="flex-bar" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      sideButtons: [
        {
          name: 'Home',
          route: '/Home',
          icon: 'hamburger.svg'
        },
        {
          name: 'Products',
          route: '/Products',
          icon: 'hamburger.svg'
        },
        {
          name: 'About',
          route: '/About',
          icon: 'hamburger.svg'
        }
      ]
    }
  }
}
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
.menu-btn {
  height: 60px;
  line-height: 60px;
  color: white;
  background: url('../assets/hamburger.svg') center center no-repeat;
  background-size: 60%;
  filter: brightness(50);
  cursor: pointer;
}
.flex-bar {
  flex: 1;
}
</style>
