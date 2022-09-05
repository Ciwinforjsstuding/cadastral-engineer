<template>
  <div class="app full-height">
    <Header :currentSection="currentSection" />
    <MainSection :observer="observer" />
    <Services :observer="observer" />
    <Certificate :observer="observer" />
    <Contacts :observer="observer" />
  </div>
</template>

<script>
import Header from './components/Header/Header.vue'
import MainSection from './components/MainSection.vue'
import Services from './components/Services/Services.vue'
import Certificate from './components/Certificate.vue'
import Contacts from './components/Contacts.vue'

export default {
  name: 'App',
  components: {
    Header,
    MainSection,
    Services,
    Certificate,
    Contacts,
  },
  data() {
    return {
      currentSection: '',
      observer: null,
      isShowFeedbackPopup: true,
    }
  },
  created() {
    this.observer = new IntersectionObserver(this.onElementObserved, {
      root: this.$el,
      threshold: 0.75,
    })
  },
  beforeDestroy() {
    this.observer.disconnect()
  },
  methods: {
    onElementObserved(entries) {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          this.currentSection = entry.target.id
        }
      })
    },
  },
}
</script>

<style>
@import 'style/index.css';

.app {
  font-size: var(--default-font-size);
  font-family: 'Montserrat', sans-serif;
}
</style>
