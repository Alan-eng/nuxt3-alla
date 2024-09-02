<template>
  <swiper
    :effect="'coverflow'"
    :grabCursor="true"
    :centeredSlides="true"
    :slidesPerView="2"
    :modules="modules"

    :loop="true"
    :coverflowEffect="{
      rotate: 0,
      stretch: 0,
      depth: 100,
      modifier: 3.5,
      slideShadows: false,
    }"
    navigation
    :pagination="{ clickable: true }"
    :scrollbar="{ draggable: true }"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
    class="MySwiper"
    :autoplay="{
      delay: 2500,
      disableOnInteraction: false,
    }"
  >
    <swiper-slide>
      <img src="/img/lilies1.png" alt="lilies1" />
    </swiper-slide>
    <swiper-slide>
      <img src="/img/lilies2.png" alt="lilies2" />
    </swiper-slide>
    <swiper-slide>
      <img src="/img/lilies3.png" alt="lilies3" />
    </swiper-slide>
    <swiper-slide>
      <img src="/img/lilies4.png" alt="lilies4" />
    </swiper-slide>
    <swiper-slide>
      <img src="/img/lilies3.png" alt="lilies3" />
    </swiper-slide>
    <swiper-slide>
      <img src="/img/lilies4.png" alt="lilies4" />
    </swiper-slide>
  </swiper>
</template>
<style scoped>
.swiper {
  width: 100%;
  padding-top: 50px;
  padding-bottom: 50px;
}

.swiper-slide {
  background-position: center;
  background-size: cover;
  width: 300px;
  /* height: 
  300px; */
}

.swiper-slide img {
  display: block;
  width: 100%;
  filter: brightness(60%);
}

.swiper-slide-active img {
  filter: none;
}

</style>
<script>
  // import Swiper core and required modules
  import { Navigation, Pagination, Scrollbar, A11y, Autoplay, EffectCoverflow } from 'swiper/modules';

  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css';
  import 'swiper/css/navigation';
  import 'swiper/css/pagination';
  import 'swiper/css/scrollbar';
  import 'swiper/css/autoplay';
  import 'swiper/css/effect-coverflow';

  // Import Swiper styles
  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
        modules: [Autoplay, EffectCoverflow, Navigation, Pagination, Scrollbar, A11y],
      };
    },
  };
</script>