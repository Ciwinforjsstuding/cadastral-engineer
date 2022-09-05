<template>
  <a :href="'#' + menuItem.href" class="mobile-menu__item">
    {{ menuItem.title }}
  </a>
</template>

<script>
export default {
  props: {
    menuItem: { type: Object, required: true },
  },
}
</script>

<style scoped>
.mobile-menu__item {
  cursor: pointer;
  padding: 10px 15px;
  border-radius: 5px;
  color: var(--white);
  text-decoration: none;
  width: 100%;
}

.mobile-menu__item:active {
  background-color: rgba(255, 255, 255, 0.447);
}
</style>
