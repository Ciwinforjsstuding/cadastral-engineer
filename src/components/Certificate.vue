<template>
  <section id="certificate" class="container certificate full-height">
    <h2 class="certificate__title">Сертификаты</h2>
    <div class="certificate-document-list">
      <img
        v-for="image in images"
        :key="image.id"
        class="certificate-document-list__item"
        :src="require(`@/assets/certificates/${image.name}`)"
      />
    </div>
  </section>
</template>

<script>
export default {
  props: {
    observer: { type: IntersectionObserver, required: true },
  },
  mounted() {
    this.observer.observe(this.$el)
  },
  computed: {
    images() {
      return [
        { id: 1, name: 'certificate.jpg' },
        { id: 2, name: 'certificate-back-side.jpg' },
        { id: 3, name: 'second-certificate.jpg' },
        { id: 4, name: 'second-certificate-back-side.jpg' },
      ]
    },
  },
}
</script>

<style scoped>
.certificate {
  margin: 0 0 60px 0;
}

.certificate:before {
  display: block;
  content: '';
  height: 55px;
  margin: -55px 0 0;
}

.certificate__title {
  margin: 0 0 110px 0;
  font-style: normal;
  font-weight: 700;
  font-size: 42px;
  line-height: 51px;
  color: var(--black);
}

.certificate-document-list {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.certificate-document-list__item {
  cursor: pointer;
  transition: 1s;
  display: block;
}

.certificate-document-list__item:hover {
  transform: scale(1.2);
}

@media screen and (max-width: 1720px) {
  .certificate {
    height: min-content !important;
  }

  .certificate-document-list {
    flex-wrap: wrap;
  }

  .certificate-document-list__item {
    margin: 15px;
  }
}

@media screen and (max-width: 610px) {
  .certificate {
    margin: 0 0 80px 0;
  }

  .certificate__title {
    text-align: center;
    margin: 0 0 50px 0;
    font-size: 36px;
  }
  .certificate-document-list {
    flex-direction: column;
  }
}
</style>
