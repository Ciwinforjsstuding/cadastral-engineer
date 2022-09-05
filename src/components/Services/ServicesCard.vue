<template>
  <div class="services-card">
    <img
      :src="require(`@/assets/services/${service.img}`)"
      class="services-card__img"
    />
    <div class="services-card-text">
      <h3 class="services-card-text__title">
        {{ service.title }}
      </h3>
      <span class="services-card-text__subtitle">
        {{ service.subtitle }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    service: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style scoped>
.services-card {
  width: 540px;
  /* width: 45%; */
  height: 200px;
  border: 5px solid var(--gray);
  border-radius: 20px;
  background-color: var(--black);
  display: flex;
  align-items: center;
  padding: 20px;
  margin: 10px;
}

.services-card__img {
  margin: 0 20px 0 0;
  width: 100px;
  height: 80px;
}

.services-card-text {
  display: flex;
  flex-direction: column;
}

.services-card-text__title {
  color: var(--white);
  font-style: normal;
  font-weight: 700;
  font-size: 36px;
  margin: 0 0 20px 0;
}

.services-card-text__subtitle {
  color: var(--gray-subtitle);
  font-style: normal;
  font-weight: 400;
  font-size: 17px;
  line-height: 21px;
}

@media screen and (max-width: 1260px) {
  .services-card-text__title {
    font-size: 24px;
  }
  .services-card-text__subtitle {
    font-size: 15px;
  }
}

@media screen and (max-width: 610px) {
  .services-card {
    width: 100%;
    margin: 10px 0;
  }
}
</style>
