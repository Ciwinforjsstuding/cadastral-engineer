<template>
  <section id="services" class="container services full-height">
    <h2 class="services__title">Услуги</h2>
    <div class="services-list">
      <ServicesCard
        v-for="service in services"
        :key="service.id"
        :service="service"
      />
    </div>
  </section>
</template>

<script>
import ServicesCard from './ServicesCard.vue'
export default {
  components: { ServicesCard },
  props: {
    observer: { type: IntersectionObserver, required: true },
  },
  mounted() {
    this.observer.observe(this.$el)
  },
  computed: {
    services() {
      return [
        {
          id: 1,
          img: 'surveying.svg',
          title: 'Межевание',
          subtitle:
            'Уточнение границ, раздел, выдел, образование, вынос границ на местности',
        },
        {
          id: 2,
          img: 'document.svg',
          title: 'Учёт объектов недвижимости',
          subtitle: 'Тех. план, акт обследования на снос',
        },
        {
          id: 3,
          img: 'deals.svg',
          title: 'Сделки',
          subtitle: 'Составление договоров купли-продаж, дарения',
        },
        {
          id: 4,
          img: 'rights.svg',
          title: 'Помощь в регистрации прав на землю и недвижимость',
          subtitle: '',
        },
      ]
    },
  },
}
</script>

<style>
.services {
  position: relative;
}

.services:before {
  display: block;
  content: '';
  height: 60px;
  margin: -50px 0 0;
}

.services__img {
  position: absolute;
  top: -30px;
  left: 0;
  right: 0;
  width: 100%;
}

.services__title {
  font-style: normal;
  font-weight: 700;
  font-size: 42px;
  z-index: 2;
  position: relative;
  color: var(--yellow);
  margin: 0 0 100px 0;
}

.services-list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  position: relative;
  z-index: 2;
}

@media screen and (max-width: 1872px) {
  .services {
    height: min-content !important;
  }

  .services-list {
    justify-content: center;
  }
}

@media screen and (max-width: 1260px) {
  .services {
    margin: 0 0 110px 0;
  }
}

@media screen and (max-width: 610px) {
  .services__title {
    text-align: center;
  }
  .services-list {
    flex-direction: column;
  }
}
</style>
