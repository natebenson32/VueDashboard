<template>
  <div class="dashboard">
    <div class="sidebar-container" :class="{ 'sidebar-closed': !sidebarOpen }">
      <div class="home-btn">
        <div class="home-container">
          <div class="home-icon" />
          <div class="home-text" :class="{ 'home-closed': !sidebarOpen }">
            HAVEN
          </div>
        </div>
      </div>
      <SideNav />
      <!-- <div class="footer"></div> -->
    </div>
    <div class="main-container">
      <NavBar @sidebar="sidebarToggle" />
    </div>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import SideNav from '@/components/SideNav.vue'

export default {
  data() {
    return {
      sidebarOpen: true
    }
  },
  components: {
    NavBar,
    SideNav
  },
  methods: {
    sidebarToggle() {
      this.sidebarOpen = !this.sidebarOpen
    }
  }
}
</script>

<style lang="less" scoped>
.dashboard {
  height: 100%;
  display: flex;
}
.sidebar-container {
  display: flex;
  flex-direction: column;
  width: 300px;
  background: rgb(18, 46, 82);
  // background: rgb(11, 33, 63);
  transition: width 0.4s;
}
.sidebar-closed {
  transition: width 0.4s;
  width: 60px;
}
.home-btn {
  flex: 1;
  height: 60px;
  background: rgb(30, 61, 100);
  cursor: pointer;
}
.home-container {
  height: 100%;
  display: flex;
  justify-content: center;
}
.home-icon {
  width: 40px;
  height: 100%;
  background: url('../assets/haven-logo.svg') center center no-repeat;
  background-size: 30px;
}
.home-text {
  width: 100px;
  font-size: 28px;
  line-height: 60px;
  color: white;
  overflow: hidden;
  transition: width 0.4s;
}
.home-closed {
  width: 0;
  transition: width 0.4s;
}
.footer {
  height: 60px;
  background: rgb(18, 46, 82);
}
.main-container {
  flex: 1;
}
</style>
