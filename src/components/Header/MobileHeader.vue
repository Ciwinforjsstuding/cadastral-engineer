<template>
  <div class="mobile-header">
    <span v-if="isOpen" class="mobile-header__title">Меню</span>
    <button @click="toggleMenu" class="burger-btn">
      <img src="@/assets/header/buger.svg" alt="мобильное меню" />
    </button>
    <nav v-if="isOpen" class="mobile-menu">
      <MobileItem
        v-for="menuItem in menuItems"
        :key="menuItem.href"
        :menuItem="menuItem"
      />
    </nav>
  </div>
</template>

<script>
import MobileItem from './MobileItem.vue'
export default {
  props: {
    menuItems: { type: Array, required: true },
  },
  data() {
    return {
      isOpen: false,
    }
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen
    },
  },
  components: { MobileItem },
}
</script>

<style scoped>
.mobile-header {
  display: none;
}

.burger-btn {
  cursor: pointer;
  background-color: var(--black);
  border: 0;
  margin: 0 0 0 95px;
  padding: 5px;
  border-radius: 5px;
}

.mobile-header__title {
  color: var(--yellow);
  font-style: normal;
  font-weight: 600;
  font-size: 32px;
}
.burger-btn:active {
  background-color: rgba(43, 43, 43, 0.3);
}

.mobile-menu {
  display: flex;
  flex-direction: column;
  position: absolute;
  width: 260px;
  height: min-content;
  top: 70px;
  right: 0;
  background-color: var(--black);
  border-radius: 0 0 10px 10px;
}

@media screen and (max-width: 360px) {
  .burger-btn {
    margin: 0 0 0 10px;
  }
}

@media screen and (max-width: 610px) {
  .mobile-header {
    display: block !important;
  }
}
</style>
