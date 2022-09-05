<template>
  <a
    :href="'#' + menuItem.href"
    :class="`header-menu__item ${isIntersectingItem}`"
  >
    {{ menuItem.title }}
  </a>
</template>

<script>
export default {
  props: {
    menuItem: { type: Object, required: true },
    currentSection: { type: String, required: true },
  },
  computed: {
    isIntersectingItem() {
      return this.menuItem.href === this.currentSection
        ? 'curretn-section'
        : ''
    },
  },
}
</script>

<style scoped>
.curretn-section {
  color: rgba(255, 255, 255, 0.694);
  background-color: rgba(255, 255, 255, 0.447);
}

.header-menu__item {
  cursor: pointer;
  padding: 10px;
  border-radius: 5px;
  color: var(--white);
  text-decoration: none;
}

.header-menu__item:hover {
  color: rgba(255, 255, 255, 0.694);
}

.header-menu__item:active {
  background-color: rgba(255, 255, 255, 0.447);
}
</style>
