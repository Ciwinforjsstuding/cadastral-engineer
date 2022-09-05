<template>
  <section id="contacts" class="contacts container">
    <img
      class="wave"
      src="@/assets/contacts/contact-wave.svg"
      alt=""
      srcset="
        @/assets/contacts/contact-wave.svg      1920w,
        @/assets/contacts/contact-wave-1260.svg 1260w,
        @/assets/contacts/contact-wave-610.svg   610w
      "
    />
    <div class="contacts-content">
      <div class="contacts-content-text">
        <h2 class="contacts-content-text__title">Контакты</h2>
        <div class="contacts-content-text-wrpapper">
          <div class="contacts-content-text-wrpapper-preson">
            <h3 class="contacts-content-text-wrpapper-preson__name">
              Смирнов Анжрей Александрович
            </h3>
            <span
              class="contacts-content-text-wrpapper-preson__exp contacts-content-text-wrpapper-preson__item"
            >
              Специалист со стажем работы более 14лет
            </span>
            <span
              class="contacts-content-text-wrpapper-preson__info contacts-content-text-wrpapper-preson__item"
              >8 (919) 045-16-42</span
            >
            <span
              class="contacts-content-text-wrpapper-preson__info contacts-content-text-wrpapper-preson__item"
              >8 (905) 698-86-53</span
            >
            <span
              class="contacts-content-text-wrpapper-preson__info contacts-content-text-wrpapper-preson__item"
              >Andrieism@mail.ru</span
            >
          </div>
          <div class="contacts-content-text-wrpapper-preson">
            <h3 class="contacts-content-text-wrpapper-preson__name">
              Иванов Игорь Александрович
            </h3>
            <span
              class="contacts-content-text-wrpapper-preson__exp contacts-content-text-wrpapper-preson__item"
            >
              Специалист со стажем работы более 17 лет
            </span>
            <span
              class="contacts-content-text-wrpapper-preson__info contacts-content-text-wrpapper-preson__item"
            >
              8 (905) 698-60-60
            </span>
            <span
              class="contacts-content-text-wrpapper-preson__info contacts-content-text-wrpapper-preson__item"
            >
              8 (905) 698-60-80
            </span>
            <span
              class="contacts-content-text-wrpapper-preson__info contacts-content-text-wrpapper-preson__item"
            >
              Igor_316@mail.ru
            </span>
          </div>
        </div>
      </div>
      <img
        src="@/assets/contacts/engineer.png"
        srcset="
          @/assets/contacts/engineer.png      1920w,
          @/assets/contacts/engineer-1260.png 1260w,
          @/assets/contacts/engineer-1260.png  610w
        "
        sizes="(max-width: 1260px) 470px"
        alt="кадастровый инженер"
        class="contacts-content__img"
      />
    </div>
    <div class="black" />
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
}
</script>

<style scoped>
.contacts {
  position: relative;
}

.contacts:before {
  display: block;
  content: '';
  height: 55px;
  margin: -55px 0 0;
}

.wave {
  position: absolute;
  left: 0;
  right: 0;
  z-index: 1;
  width: 100%;
  z-index: 1;
  top: -110px;
}

.contacts-content {
  display: flex;
  justify-content: space-between;
  position: relative;
  z-index: 2;
}

.contacts-content-text {
  color: var(--white);
}

.contacts-content-text__title {
  color: var(--yellow);
  font-style: normal;
  font-weight: 700;
  font-size: 42px;
  margin: 20px 0 50px 0;
}

.contacts-content-text-wrpapper-preson {
  display: flex;
  flex-direction: column;
  font-style: normal;
  font-size: 20px;
  line-height: 24px;
  font-weight: 600;
  margin: 0 0 70px 0;
}

.contacts-content-text-wrpapper-preson__item {
  margin: 10px 0;
  font-weight: 500;
}

.contacts-content__img {
  object-fit: cover;
  height: 600px;
}

@media screen and (max-width: 1260px) {
  .wave {
    top: 0;
  }

  .contacts-content__img {
    height: 470px;
  }

  .contacts-content {
    align-items: center;
  }

  .contacts-content-text-wrpapper-preson__item {
    margin: 5px 0;
    font-size: 15px;
  }

  .contacts-content-text__title {
    margin: 60px 0 30px 0;
  }
}

@media screen and (max-width: 610px) {
  .contacts-content-text-wrpapper {
    display: flex;
  }

  .contacts-content-text__title {
    font-size: 40px;
    margin: 0 0 30px 0;
  }

  .contacts-content-text-wrpapper-preson__item {
    font-size: 13px;
  }

  .contacts-content__img {
    height: 160px;
    position: absolute;
    right: 0;
    bottom: 0;
  }
}

@media screen and (max-width: 480px) {
  .contacts-content-text-wrpapper {
    flex-direction: column;
  }

  .contacts-content-text-wrpapper-preson {
    margin: 0 0 10px 0;
  }

  .contacts-content__img {
    bottom: -100px;
  }
  .black {
    width: 100%;
    height: 55vh;
    background-color: var(--black);
    position: absolute;
    right: 0;
    left: 0;
    top: 20vh;
  }
}
@media screen and (max-width: 360px) {
}
</style>
