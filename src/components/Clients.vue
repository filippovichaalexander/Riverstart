<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Grid, Pagination, Navigation } from 'swiper/modules';
const modules = [ Grid, Pagination, Navigation ];
import 'swiper/css';
import 'swiper/css/grid';
import 'swiper/css/pagination';
import 'swiper/css/navigation';

import { defineProps } from 'vue'


const props = defineProps({
  clients: {
    type: Array,
    default: () => ([])
  }
})

</script>

<template>
  <div class="clients">
    <div class="container">
      <div class="clients__inner">
        <h2 class="clients__title">Наши клиенты</h2>
          <Swiper
            :navigation= "true"
            :modules="modules" 
            :slidesPerView="3"
            :grid="{rows: 3, fill: column}"
            :spaceBetween="30"
            :breakpoints="{
              '360': {
                grid: {
                  rows: 3
                },
                slidesPerView: 2,
                navigation: {
                  enabled: false
                }
              },
               '768': {
                grid: {
                  rows: 2,
                },
                slidesPerView: 3,
                navigation: {
                  enabled: false
                }
              },
              '1280': {
                grid: {
                  rows: 2,
                },
                slidesPerView: 4,
                navigation: {
                  enabled: true
                }
              }
            }"
            class="mySwiper">
            <swiper-slide class="clients__item" v-for="client in clients" :key="client.id">
                <img :src="client.image" :alt="client.alt" class="clients__item-logo">
                <p class="clients__item-text">{{client.text}}</p>
            </swiper-slide>
          </swiper>
          <div class="clients__hint">
            <div class="clients__hint-left">
              <img src="../assets/images/person-icon.png" alt="chat" class="clients__hint-icon">
            </div>
            <div class="clients__hint-right bubble">
              <p class="clients__hint-right-text">Среднее время работы с клиентом — 5 лет</p>
            </div>
          </div>
      </div>
    </div>
  </div>  
</template>


<style lang="scss" scoped>
@import '../assets/styles/base.scss';

@import 'swiper/css';
@import 'swiper/css/navigation';
@import 'swiper/css/pagination';
@import 'swiper/css/scrollbar';
@import 'swiper/css/grid';

.swiper.prevEl {
  display: block;
}

  .swiper-button-next {
    width: 92px !important;
    height: 92px !important;
    border-radius: 50% !important;
    background-color: $primary !important;
  }

.mySwiper {
  width: 100%;
  height: 100%;
  margin-left: auto;
  margin-right: auto;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  align-items: center;
  height: 94px;
}
.clients {
  padding-top: 3.375rem;
  font-family: 'MabryPro', sans-serif;
  background-color: $color-background2;
  &__inner {
    display: flex;
    flex-direction: column;
    align-items: baseline;
  }
  &__title {
    margin-bottom: 3.813rem;
    color: $color-grey2;

    font-size: 2.625rem;
    line-height: 4.2rem;
    font-weight: 400;
    letter-spacing: -3%;
  }
  &__slider {
    display: grid;
    justify-items: start;
    align-items: start;
    grid-template-columns: repeat(3, 9.625rem);
    gap: 4.625rem 4.625rem;
    overflow-x: scroll;
    width: 100%;
    &::-webkit-scrollbar {
      display: none;
    }
  }
  &__item-logo {
    width: 9.625rem;
  }
  &__item-text {
    color: $color-grey1;
    text-align: center;
    font-size: 0.813rem;
    line-height: 1rem;
    font-weight: 400;
    letter-spacing: 2%;
  }
  &__hint {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 53px;
  }
  &__hint-left {
    width: 66px;
    height: 66px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    background:transparent;
    margin-right: 10px;
  }
  &__hint-right-text {
    color: $color-black1;
    font-size: 1rem;
    line-height: 1.313rem;
    font-weight: 400;
  }
  // chat Bubble
  .bubble {
   position: relative;
   max-width: 250px;
   padding: 16px 21px 15px 31px;
   background: $color-grey2;
   -webkit-border-radius: 10px;
   -moz-border-radius: 10px;
   border-radius: 15px;
}

.bubble:after
  {
    content: '';
    position: absolute;
    clip-path: polygon(100% 36%, 0 9%, 100% 100%);
    display: block;
    width: 10px;
    height: 10px;
    background-color: $color-grey2;
    z-index: 1;
    left: -9px;
    top: 36px;
  }
}

@media (min-width: 1280px)  {
  
.swiper .swiper-button-next {
  color: red !important;
}
  .swiper-button-next {
    width: 92px !important;
    height: 92px !important;
    border-radius: 50% !important;
    background-color: $primary !important;
  }
}

@media (min-width: 1280px)  {
  .clients {
    &__item-logo {
        width: 12.625rem;
      }
  }

}

</style>