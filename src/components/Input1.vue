<script setup>
import { ref, defineProps, defineEmits } from 'vue'

const props = defineProps({
  modelValue: {
    type: String,
    required: true
  },
  placeholder: {
    type: String,
    default: 'Placeholder'
  },
  active: {
    type: Boolean,
    default: false
  },
  type: {
    type: String,
    default: ''
  }
})
const emit = defineEmits(['update:modelValue', 'update:active'])
let valid = ref(true)

const input = ref(null)

// Цвет placeholder при вводе данных 
let actived = ref(false)

const handleInput = (event) => {
  if(props.modelValue.value != '') {
    actived = true
    // email mask
//     let maskid = event.target.value.replace(/^(.)(.*)(.@.*)$/,
//      (_, a, b, c) => a + b.replace(/./g, '*') + c
// );
  if(props.type === 'email') {
      const regex = new RegExp('[a-z0-9]+@[a-z]+\.[a-z]{2,3}');
      let result = regex.test(event.target.value);
      
      if(result) {
        valid = true
      } else valid = false
    } else if(props.type === 'tel') {
      const regex = /^[\+]?[(]?[0-9]{3}[)]?[-\s\.]?[0-9]{3}[-\s\.]?[0-9]{4,6}$/im;
      let result = regex.test(event.target.value);
      let x = event.target.value.replace(/\D/g, '').match(/(\d{0,3})(\d{0,3})(\d{0,4})/);
      event.target.value = !x[2] ? x[1] : '(' + x[1] + ') ' + x[2] + (x[3] ? '-' + x[3] : '');

      if(result) {
        valid = true
      } else valid = false
    }
      emit('update:modelValue', event.target.value)
      emit('update:active', true)
    } else emit('update:active', false)
  }
  const handleFocus = () => {
    emit('update:active', true)
  }
  const handleBlur = () => {
    if(props.modelValue) {
      emit('update:active', true)
      actived = false
    } else {
      emit('update:active', false)
      valid = true
      actived = false
    }
  } 
</script>

<template>
  <div class="input">
    <p class="input__placeholder" 
      :class="[active ? 'active' : 'disabled', actived ? 'actived' : 'unactived']">
      {{ props.placeholder }}</p>
    <input 
      required
      :type="type" 
      class="input__inner"
      :class="valid == false ? 'error' : ''"
      :value="props.modelValue"
      @input="handleInput" 
      @focus="handleFocus" 
      @blur="handleBlur"/>
      <p class="input__hint" v-if="valid == false">Вы ввели неверные данные</p>
      <!-- <p class="hint" v-else-if="valid == true">ok</p>  -->
  </div>
</template>

<style lang="scss" scoped>
  @import '../assets/styles/base.scss';
  @import '../assets/styles/input.scss';

  .active {
    transform: scale(0.6);
  }
  .actived {
    color: $primary;
  }
  .unactived {
    color: $color-grey1;
  }
  .disabled {
    transform: scale(1);
  }
  .error {
    border-bottom: 1px solid $color-red !important;
  }
  .show {
    opacity: 1 !important;
  }
</style>