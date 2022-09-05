<template>
  <section id="main" class="main container full-height">
    <div class="main-wrapper">
      <div class="main-text">
        <h2 class="main__title">Замеры имеют значение!</h2>
        <span class="main__subtitle"
          >Более 15 лет исправной работы</span
        >
      </div>
      <div class="main-bg-img__wrapper">
        <img
          src="@/assets/main/main-house.jpg"
          srcset="
            @/assets/main/main-house.jpg      1920w,
            @/assets/main/main-house-1260.jpg  760w,
            @/assets/main/main-house-610.jpg   610w
          "
          class="main-bg-img"
        />
      </div>
    </div>
    <img
      class="main__wave"
      src="@/assets/main/main-wave.svg"
      srcset="
        @/assets/main/main-wave.svg      1920w,
        @/assets/main/main-wave-1260.svg 1260w,
        @/assets/main/main-wave-610.svg   610w
      "
      alt="волна"
    />
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

<style>
.main {
  position: relative;
}
.main__title {
  font-style: normal;
  font-weight: 800;
  font-size: 64px;
  color: var(--black);
  margin: 0 0 50px 0;
}
.main__subtitle {
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  color: var(--gray);
}

.main__wave {
  position: absolute;
  z-index: 1;
  left: 0;
  right: 0;
  width: 100%;
  bottom: -90%;
}

.main-wrapper {
  display: flex;
}

.main-text {
  margin: 100px 0 0 0;
}

.main__top-wave {
  position: absolute;
  left: 0;
  right: 0;
  width: 100%;
  bottom: 0;
}

.main-bg-img__wrapper {
  width: 60%;
}

.main-bg-img {
  height: 85vh;
  object-fit: cover;
}

@media screen and (max-width: 1260px) {
  .main__wave {
    bottom: -50%;
  }

  .main__title {
    font-size: 42px;
    margin: 0 0 10px 0;
    text-align: center;
  }

  .main__subtitle {
    font-size: 20px;
    text-align: center;
    display: block;
  }

  .main-wrapper {
    flex-direction: column;
  }

  .main-text {
    margin: 100px 0 0 0;
  }
}

@media screen and (max-width: 610px) {
  .main-bg-img {
    height: 85vh;
    width: 100%;
    position: absolute;
    right: 0;
  }

  .main__wave {
    bottom: -50%;
  }
}

@media screen and (max-width: 480px) {
  .main__wave {
    bottom: -35%;
  }
}
@media screen and (max-width: 360px) {
  .main__wave {
    bottom: -30%;
  }
}
</style>
