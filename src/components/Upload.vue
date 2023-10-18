<script setup>

import { ref, defineProps, defineEmits, computed } from 'vue'

const props = defineProps({
  modelValue: {
    type: null,
    required: true
  }
})
const convertedFileSize = computed(() => {
  return props.modelValue.size / 1000
})

let sizeAccepted = ref('null')
const emit = defineEmits(['update:modelValue'])
const handleInput = (event) => {
  emit('update:modelValue', event.target.files[0])
  const fsize = event.target.files[0].size;
    if(fsize <= 100000) {
    sizeAccepted = 'passed'
  } else sizeAccepted = 'notPassed'

}
const deleteFile = () => {
  emit('update:modelValue', null)
  console.log('modelValue', props.modelValue)
  sizeAccepted = 'null'

}
</script>

<template>
  <div class="upload">
    <label class="upload__inner upload--label">
      <img src="../assets/images/upload-icon.svg" 
      alt="upload file" 
      class="upload__icon">
      <p class="upload__text">Прикрепить бриф</p>
      <input type="file" class="upload__input" @change="handleInput">
    </label>
    <a href="#" class="upload__inner upload--link">
      <img src="../assets/images/link-doc-icon.svg" alt="cloud document" class="upload__doc-icon">
      <p class="upload__doc-text">Наш бриф в Google Docs</p>
      <img src="../assets/images/link-arrow-icon.svg" alt="cloud link" class="upload__link-icon">
    </a>
  </div>
  <div class="response">
    <div class="response__answer" v-if="sizeAccepted === 'passed'">
      <div class="response__info response--info-valid">
        <img src="../assets/images/response-ok-icon.svg" alt="document" class="response__info-icon">
        <p class="response__info-text">Бриф на разработку сервиса (PDF, {{convertedFileSize}} MB)</p>
      </div>
      <div class="response__btn-wrapper">
        <div class="response__close-icon"></div>
        <button class="response__btn" @click="deleteFile">Удалить</button>
      </div>
    </div>
    <p class="response__info response--info-unvalid" v-else-if="sizeAccepted === 'notPassed'">Превышен максимальный размер файла</p>
  </div>
</template>



<style lang="scss" scoped>
@import '../assets/styles/base.scss';

.upload {
  margin-top: 2.25rem;
  font-family: 'MabryPro', sans-serif;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  font-size: 1.25rem;
  line-height: 1.875rem;
  color: $color-black1;
  &__inner {
    height: 1.313rem;
    display: flex;
    align-items: center;
  }
  &--label {
    gap: 0.94rem;
    position: relative;
  }
  &__input {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
    visibility: hidden;
  }
  &:hover {
    cursor: pointer;
  }
  &--link {
    margin-left: 3.75rem;
    color: $color-black1;
    display: none;
  }
  &__doc-text {
    margin-left: 0.563rem;
    margin-right: 0.313rem;
  }
}
  .response {
    &__answer {
      display: flex;
      align-items: center;
      justify-content: flex-start;
    }
    &__info {
      padding: 0.75rem 1rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.938rem;
      border-radius: 0.5rem;

      font-size: 1.25rem;
      line-height: 1.875rem;

    }
    &--info-valid {
      background-color: $color-blue1;
      margin-right: 1rem;
      color: $primary;
    }
    &--info-unvalid {
      background-color: $color-red1;
      color: $color-red;
    }
    &__close-icon {
      border-color: $color-black1;
    }
    &__btn-wrapper {
      padding: 0.5rem 0;
      color: $color-black1;

      font-size: 1rem;
      line-height: 1.5rem;
      font-weight: 400;
    }
  }
  
@media (min-width: 768px)  {
  .upload {
    margin-top: 36px;
  }
}

@media (min-width: 1920px)  {
  .upload {
    margin-top: 61px;
  }
}
</style>