<template>
  <div class="side-nav">
    <div class="static-bar">
      <div class="home-side-btn">
        <div class="menu-icon"></div>
        <transition name="menu-text">
          <div class="menu-btn-text" v-if="open">Home</div>
        </transition>
      </div>
      <div
        class="menu-btn"
        :class="{ 'home-btn': item.name === 'Home' }"
        v-for="(item, index) in sideButtons"
        :key="index"
      >
        <div class="menu-icon"></div>
        <transition name="menu-text">
          <div class="menu-btn-text" v-if="open">{{ item.name }}</div>
        </transition>
      </div>
    </div>
    <div class="flex-bar"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sideButtons: [
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
  },
  props: {
    open: {
      type: Boolean,
      required: true,
      default: true
    }
  }
}
</script>

<style lang="less">
.side-nav {
  height: 100%;
  display: flex;
  overflow: hidden;
}
.static-bar {
  width: 100%;
}
.home-side-btn {
  display: flex;
  border-bottom: 2px solid rgba(255, 255, 255, 0.1);
  cursor: pointer;
}
.menu-btn {
  width: 100%;
  display: flex;
  cursor: pointer;
}
.menu-btn:hover,
.home-side-btn:hover {
  background: rgb(30, 61, 100);
}
.menu-icon {
  width: 60px;
  height: 60px;
  line-height: 60px;
  color: white;
  margin-right: 5px;
  background: url('../assets/hamburger.svg') center center no-repeat;
  background-size: 50%;
  filter: brightness(50);
}
.menu-btn-text {
  width: 240px;
  line-height: 60px;
  text-align: left;
  font-size: 20px;
  color: white;
  // overflow: hidden;
}
.menu-btn-closed {
  width: 0;
}
.flex-bar {
  flex: 0;
}

// Transitions
.menu-text-enter-active {
  transition: all 0.3s;
  transition-delay: 0.1s;
}
.menu-text-leave-active {
  transition: opacity 0.3s;
}
.menu-text-enter, .menu-text-leave-to /* .fade-leave-active below version 2.1.8 */ {
  width: 0;
  opacity: 0;
}
</style>
