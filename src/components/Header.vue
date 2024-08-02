<template>
  <div class="header-container">
    <div>
      <img src="../assets/3.jpeg" width="80" alt="logo">
    </div>
    <div>
      <span class="icon-container">
        <i class="fab fa-facebook icon"></i>
      </span>
      <span class="icon-container">
        <i class="fab fa-tiktok icon"></i>
      </span>
      <span class="icon-container">
        <i class="fab fa-instagram icon"></i>
      </span>
    </div>
    <div class="menu-container">
      <button class="menu-toggle" @click="toggleMenu">
        <div :class="{'bar': true, 'active': isActive}"></div>
        <div :class="{'bar': true, 'active': isActive}"></div>
        <div :class="{'bar': true, 'active': isActive}"></div>
      </button>
      <div v-if="isActive" class="menu">
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import '@fortawesome/fontawesome-free/css/all.css';

export default {
  name: 'Header',
  props: {
    
  },

  data() {
    return {
      isActive: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isActive = !this.isActive;
    },
  },
}
</script>

<style scoped>
.header-container {
  position: relative;
  display: flex;
  padding: 25px;
  justify-content: space-between;
  align-items: center;
}

.icon-container {
  background-color: black;
  padding: 15px;
  border-radius: 50%;
  margin: 0px 5px;
}

.icon {
  color: #EFC756;
  font-size: 15px;
}

.menu-container {
  
}

.menu-toggle {
  display: flex;
  flex-direction: column;
  cursor: pointer;
  border: none;
  background: transparent;
}

.bar {
  width: 30px;
  height: 3px;
  background-color: #333;
  margin: 5px 0;
  transition: all 0.3s;
}

.bar.active:nth-child(1) {
  transform: rotate(45deg) translate(10px, 10px);
}

.bar.active:nth-child(2) {
  opacity: 0;
}

.bar.active:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -8px);
}

.menu {
  position: absolute;
  background-color: #A0A09F;
  min-height: 100vh;
  min-width: 100vw;
  left: -200px;
  top: 0
}
</style>
