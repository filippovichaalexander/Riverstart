<script setup>
import { ref } from 'vue'

import internormLogo from '../assets/images/internorm-logo.svg'
import rosatomLogo from '../assets/images/rosatom-logo.svg'
import labchevskyLogo from '../assets/images/labchevsky-logo.svg'
import gazLogo from '../assets/images/gaz-logo.svg'
import gaspromLogo from '../assets/images/gasprom-logo.svg'
import mrdoorsLogo from '../assets/images/mrdoors-logo.svg'
import bonafideLogo from '../assets/images/bonafide-logo.svg'
import universityLogo from '../assets/images/university-logo.svg'

const inputName = ref('')
const activeName = ref(false)

const inputEmail = ref('')
const activeEmail = ref(false)
const typeEmail = ref('email')

const inputTel = ref('')
const activeTel = ref(false)
const typeTel = ref('tel')

const inputTask = ref('')
const activeTask = ref(false)

const typeText = ref('text')

const uploadedFile = ref(null)

let loading = ref(null)

let modalVisible = ref(false)


const showModal = () => {
  loading = true
  const load = setTimeout(() => {
    loading = false
    modalVisible.value = true
  }, 2000) 

  // default inputs
inputName = ref('')
inputEmail = ref('')
inputTel = ref('')
inputTask = ref('')
}

const clients = ref([
  {
    id: 1,
    text: '5 лет вместе',
    image: internormLogo,
    alt: 'internorm'
  },
  {
    id: 2,
    text: '1 год вместе',
    image: rosatomLogo,
    alt: 'rosatom'
  },
  {
    id: 3,
    text: '1 год вместе',
    image: labchevskyLogo,
    alt: 'labchevsky'
  },
  {
    id: 4,
    text: '1 год вместе',
    image: gazLogo,
    alt: 'gaz'
  },
  {
    id: 5,
    text: '1 год вместе',
    image: gaspromLogo,
    alt: 'gasprom'
  },
  {
    id: 6,
    text: '2 года вместе',
    image: mrdoorsLogo,
    alt: 'mrdoors'
  },
  {
    id: 7,
    text: '1 год вместе',
    image: bonafideLogo,
    alt: 'bonafide'
  },
  {
    id: 8,
    text: '5 лет вместе',
    image: universityLogo,
    alt: 'university'
  },
  {
    id: 9,
    text: '5 лет вместе',
    image: internormLogo,
    alt: 'internorm'
  }
])

const interests = ref([
  {
    id: 1,
    name: 'Сайт',
    selected: false,
    type: 'interest'
  },
  {
    id: 2,
    name: 'Веб-сервис',
    selected: false,
    type: 'interest'
  },
  {
    id: 3,
    name: 'Маркетинг',
    selected: false,
    type: 'interest'
  },
  {
    id: 4,
    name: 'Приложение',
    selected: false,
    type: 'interest'
  },
  {
    id: 5,
    name: 'Брендинг',
    selected: false,
    type: 'interest'
  },
  {
    id: 6,
    name: 'Что-то ещё',
    selected: false,
    type: 'interest'
  }

])

const budgets = ref([
  {
    id: 1,
    name: 'До 500к',
    value: '1',
    selected: false,
    className: 'left',
    type: 'budget'
  },
  {
    id: 2,
    name: 'До 500к',
    value: '2',
    selected: false,
    className: 'center',
    type: 'budget'
  },
  {
    id: 3,
    name: '> 1млн',
    value: '3',
    selected: false,
    className: 'right',
    type: 'budget'
  }
])
import Input from './Input1.vue'
import Upload from './Upload.vue'
import Button from './Button.vue'
import ButtonBudget from './ButtonBudget.vue'
import Modal from './Modal.vue'

</script>

<template>
  <form class="form">
    <div class="preloader spinner" v-if="loading == true"></div>
    <div class="wrapper">
      <Modal v-model="modalVisible" v-if="modalVisible" />
      <div class="form__container" v-else>
        <div class="form__inner">
          <h2 class="form__title">Что вас интересует</h2>
          <div class="form__btns-interest">
            <Button 
              class="form__btn" 
              v-for="interest in interests" 
              :key="interest.id" 
              :interest="interest"
              v-model="interest.selected"/>
          </div>
          <div class="inputs">
            <div class="inputs__row">
              <Input 
                class="inputs__row-item inputs--row--item1"
                placeholder="Имя"
                :type="typeText"
                v-model="inputName"
                v-model:active="activeName"
              />
              <Input 
                class="inputs__row-item inputs--row--item2"
                placeholder="Почта"
                :type="typeEmail"
                v-model="inputEmail"
                v-model:active="activeEmail"
              />
            </div>
            <Input 
              class="phone"
              placeholder="Телефон"
              :type="typeTel"
              v-model="inputTel"
              v-model:active="activeTel"
            />
            <Input 
              placeholder="Опишите задачу"
              :type="typeText"
              v-model="inputTask"
              v-model:active="activeTask"
            />
            <h2 class="form__title">Бюджет (&#8381;)</h2>
            <div class="btn-group">
              <ButtonBudget 
                v-for="budget in budgets" 
                :key="budget.id" 
                :budget="budget"
                v-model="budget.selected"/>
            </div>
          </div>
        </div>
        <Upload v-model="uploadedFile"/>
        <input 
        class="btn btn--default btn--mb-lg" 
        type="submit" 
        value="Оставить заявку"
        @click.prevent="showModal"/>
        <div class="politics">
          <p class="politics__top">
            Нажав на кнопку, вы соглашаетесь с &nbsp;
          </p>
          <a href="#" class="politics__bottom">
            политикой обработки персональных данных
          </a>
        </div>
      </div>
    </div>  
    </form>
</template>

<style lang="scss" scoped>
  @import '../assets/styles/base.scss';
  @import '../assets/styles/button.scss';

// preloader
.spinner{
    width: 80px;
    height: 80px;
    
    border: 10px solid #f3f3f3;
    border-top:10px solid rgba(49, 45, 255, 60%);
    border-radius: 100%;
    
    position: absolute;
    top:0;
    bottom:0;
    left:0;
    right: 0;
    margin: auto;
    
    animation: spin 1s infinite linear;
}

@keyframes spin {
    from{
        transform: rotate(0deg);
    }to{
        transform: rotate(360deg);
    }
}

// preloader
  .main-wrapper {
    
  background-color: $color-background2;
  }
  
  .form {
    background-color: $color-grey2;
    padding-top: 30px;
    padding-bottom: 4.063rem;
    &__container {
      padding: 0 30px;
      margin: 0 auto;
    }
    &__title {
      padding-bottom: 15px;
      font-size: 0.938rem;
      line-height: 1.5rem;
      letter-spacing: 1%;

      color: $color-grey1;
    }
    &__btns-interest {
      padding-bottom: 50px;
      display: flex;
      align-items: center;
      justify-content: flex-start;
      overflow-x: scroll;
      position: relative;
      &::-webkit-scrollbar {
        display: none;
      }
    }
    &
    &__btn {
      &:not(:nth-child(6n)) {
        margin-right: 7px;
      }
    }
  }
  .politics {
    font-size: 0.75rem;
    font-weight: 400;
    line-height: 1.125rem;
    letter-spacing: 1%;
    &__top {
      color: rgba(21, 20, 26, 40%)
    }
    &__bottom {
      color: $color-black2;
      &:hover {
        color: $primary;
      }
    }
  }
  
@media (min-width: 768px)  {
  .politics {
    display: flex;
    flex-direction: row;
    align-items: center;
  }
  .form {
    border-top: 50px;
    padding-bottom: 87px;
    &__btns-interest {
      padding-bottom: 60px;
    }
    &__container {
      padding: 0 40px;
      margin: 0 auto;
    }
  }
  .inputs {
    &__row {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    &__row-item {
      width: 48%;
    }
    &--row-item1 {
      margin-right: 36px;
    }
  }
}
@media (min-width: 768px)  {
  .form {
    &__container {
      padding: 0 63px;
      margin: 0 auto;
    }
    &__btns-interest {
      max-width: 510px;
      flex-wrap: wrap;
      gap: 13px;
    }
  }
}

@media (min-width: 1920px)  {
  .form {
    padding-top: 132px;
    padding-bottom: 80px;
    &__container {
      padding: 0 220px 0 63px;
      margin: 0 auto;
    }
    &__btns-interest {
      max-width: 510px;
      flex-wrap: wrap;
      gap: 13px;
    }
  }
  .phone {
    margin-bottom: 182px;
  }
}
</style>