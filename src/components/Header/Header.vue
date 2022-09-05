<template>
  <header class="header container">
    <img
      class="header__logo"
      src="@/assets/header/header-logo.png"
      srcset="@/assets/header/header-logo.png 1920w"
      alt="лого"
    />
    <nav class="header-menu">
      <HeaderItem
        v-for="menuItem in menuItems"
        :key="menuItem.herf"
        :menuItem="menuItem"
        :currentSection="currentSection"
      />
    </nav>
    <MobileHeader :menuItems="menuItems" />
  </header>
</template>

<script>
import HeaderItem from './HeaderItem.vue'
import MobileHeader from './MobileHeader.vue'
export default {
  components: {
    HeaderItem,
    MobileHeader,
  },
  props: {
    currentSection: { type: String, required: true },
  },
  computed: {
    menuItems() {
      return [
        { href: 'main', title: 'Главная' },
        { href: 'services', title: 'Услуги' },
        { href: 'certificate', title: 'Сертификаты' },
        { href: 'contacts', title: 'Контакты' },
      ]
    },
  },
}
</script>

<style>
.header {
  position: fixed;
  z-index: 3;
  color: var(--white);
  background-color: var(--black);
  height: 70px;
  display: flex;
  align-items: center;
  width: 100%;
}

.header__logo {
  height: 50px;
  flex-basis: 15%;
}

.header-menu {
  display: flex;
  flex-basis: 85%;
  justify-content: space-around;
  align-items: center;
}

@media screen and (max-width: 610px) {
  .header {
    display: flex;
    justify-content: space-between;
  }
  .header-menu {
    display: none;
  }
}
</style>
