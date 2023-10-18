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
const typeText = ref('text')

const inputEmail = ref('')
const activeEmail = ref(false)
const typeEmail = ref('email')

const inputTel = ref('')
const activeTel = ref(false)
const typeTel = ref('tel')

const uploadedFile = ref(null)

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
  },
  {
    id: 10,
    text: '5 лет вместе',
    image: labchevskyLogo,
    alt: 'internorm'
  },
  {
    id: 11,
    text: '1 год вместе',
    image: rosatomLogo,
    alt: 'rosatom'
  },
  {
    id: 12,
    text: '1 год вместе',
    image: labchevskyLogo,
    alt: 'labchevsky'
  }
])

import Clients from './Clients.vue'
import Projects from './Projects.vue'
import Form from './Form.vue'
import Contacts from './Contacts.vue'
import Footer from './Footer.vue'
</script>

<template>
  <div class="main-wrapper">
    <Clients :clients="clients"/>
    <div class="main__middle-wrapper">
        <div class="laptop-wrapper">
          <Projects class="main__middle-item main--left-item"/>
          <Contacts class="laptop"/>
        </div>
        <Form class="main__middle-item main--right-item" />
    </div>
    <Contacts class="mobile"/>
    <Footer />
      
  </div>
</template>

<style lang="scss" scoped>
  @import '../assets/styles/base.scss';
  @import '../assets/styles/button.scss';

  .main-wrapper {
    
    overflow-x: hidden;
    background-color: $color-background2;
  }
  .laptop {
    display: none;
  }

  @media (min-width: 1280px)  {
    .container--laptop {
      padding-right: 0;
      padding-left: 40px;
    }
    .main {
      &__middle-wrapper {
        display: flex;
        align-items: flex-end;
        justify-content: space-between;
      }
    }
    .main--right-item {
      width: 50%;
      margin-left: 50px;
    }
    .laptop-wrapper {
      width: 50%;
    }
    .laptop {
      display: block;
    }
    .mobile {
      display: none;
    }
  }

  @media (min-width: 1280px)  {
    .main__middle-wrapper {
      padding-right: 0;
      padding-left: 40px;
    }
    .main--right-item {
        width: 55%;
        margin-left: 50px;
      }
      .laptop-wrapper {
        width: 45%;
      }
  }
  
  @media (min-width: 1920px)  {
    .main__middle-wrapper {
      padding-right: 0;
      padding-left: 80px;
    }
    .laptop-wrapper {
        width: 611px;
      }
  }
</style>