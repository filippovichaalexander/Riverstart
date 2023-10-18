<script setup>
import { ref, defineProps, defineEmits } from 'vue'

const props = defineProps({
  modelValue: {
    type: Boolean
  }
})
const emit = defineEmits(['update:modelValue'])

const handleClose = (e) => {
  console.log(e)
  e.preventDefault()
  emit('update:modelValue', false)
}

</script>
<template>
  <div class="modal" v-if="props.modelValue">
    <div class="container">
      <div class="modal__inner" >
        <button class="btn-close" @click="handleClose">X</button>
        <div class="modal__icon-wrapper">
          <img src="../assets/images/error-icon.svg" alt="" class="modal__icon">
        </div>
        <h2 class="modal__title">
          Произошла ошибка <br> при отправке
        </h2>
        <p class="modal__text">
          К сожалению, произошла ошибка при отправке вашего сообщения.
           Пожалуйста, проверьте ваше подключение 
           к интернету и попробуйте отправить сообщение еще раз
        </p>
        <button
        class="btn btn--default btn--mb-lg" 
        @click.prevent="handleClose">Отправить заново</button>
      </div>
    </div> 
  </div>
  
</template>


<style lang="scss" scoped>
@import '../assets/styles/base.scss';
.btn-close {
  position: absolute;
  right: 92px;
  top: 92px;
}
.modal {
  color: $color-black2;
  
  &__inner {
    position: relative;
  }
  &__title {
    margin: 3.5rem 0;
    font-size: 3.81rem;
    font-weight: 400;
    line-height: 4.75rem;
  }
  &__text {
    font-size: 1.625rem;
    font-weight: 400;
    line-height: 2.563rem;
  }
  &__icon-wrapper {
    border-radius: 50%;
    background-color: $color-green;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 80px;
    height: 80px;
  }
}
  .container {
    width: 100%;
    padding: 92px;
  }
</style>