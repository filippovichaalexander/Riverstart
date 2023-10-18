<script setup>
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
  modelValue: {
    type: Boolean
  },
  interest: {
    type: Object,
    default: () => ({})
  }
})
const emit = defineEmits(['update:modelValue'])

const handleInput = () => {
  if(!props.modelValue) {
    emit('update:modelValue', true)
  } else if(props.modelValue) {
    emit('update:modelValue', false)
  }
}

</script>

<template>
  <label
    class="btn-wrapper btn btn--sm btn--bordered" 
    :class="props.modelValue ? 'active' : 'unactive'">
    {{props.interest.name}}
    <input type="checkbox" class="btn-input" @change="handleInput" >
  </label>
</template>


<style lang="scss" scoped>
  @import '../assets/styles/base.scss';
  @import '../assets/styles/button.scss';

  .btn-wrapper {
    position: relative;
  }
  .btn-input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
  }
  .active {
    background-color: $primary;
    color: $color-grey2;
  }
  .unactive {
    color: $color-black1 !important;
    background-color: $white !important;
  }
</style>

