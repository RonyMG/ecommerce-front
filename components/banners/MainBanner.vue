<template>

    <div class="main-banner__comp">

        <div ref="siemaContainer" class="main-section-mb">
            <div v-for="(slideObject, index) in slideObjects" :key="index" class="siema-slide main-banner__container">
                <NuxtLink :href="slideObject.href" class="main-banner" :class="`main-banner__dist-${slideObject.distribution}`" :style="{ backgroundImage: `url(${slideObject.imageUrl})` }">
                  <div class="main-container">
                    <div class="main-banner__info">
                        <h1 class="main-banner__h1">{{ `${slideObject.title}` }}</h1>
                        <p class="main-banner__p">{{ slideObject.description }}</p>
                    </div>
                  </div>
                </NuxtLink>
            </div>
        </div>
        <div class="main-banner__controls">
            <button class="main-banner__button" @click="movePrev">&lt;</button>
            <button class="main-banner__button main-banner__button--next" @click="moveNext">&gt;</button>
        </div>
    </div>
</template>

<script>

import Siema from 'siema';

export default {
  data() {
    return {
      slideObjects: [
        { title: 'logotipo', description: 'Descripcion referente al primer slide.', imageUrl: '_nuxt/static/images/banner-example-3.png', href: '/locations', distribution: 'left' },
        { title: 'promoción', description: 'Descripcion referente al segundo slide.', imageUrl: '_nuxt/static/images/banner-example-3.png', href: '/locations', distribution: 'center' },
        { title: 'anuncio largo y extenso exclusivo', description: 'Conoce nuestras mejores ofertas pensadas exclusivamente para ti, encuentra lo que siempre buscaste!, Conoce nuestras mejores ofertas pensadas exclusivamente para ti, encuentra lo que siempre buscaste!, Conoce nuestras mejores ofertas pensadas exclusivamente para ti, encuentra lo que siempre buscaste!', imageUrl: '_nuxt/static/images/banner-example-3.png', href: '/locations', distribution: 'right' }
      ],
      siema: null
    };
  },
  mounted() {
    this.siema = new Siema({
      selector: this.$refs.siemaContainer,
      loop: true,
      draggable: false,
      duration: 700,
    });
  },
  beforeDestroy() {
    if (this.siema) {
      this.siema.destroy();
    }
  },
  methods: {
      movePrev() {
          if (this.siema) {
              this.siema.prev();
          }
      },
      moveNext() {
          if (this.siema) {
              this.siema.next();
          }
      }
  }
}
</script>
  
  <style>

  </style>
  