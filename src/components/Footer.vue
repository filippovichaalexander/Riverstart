<script setup>

</script>

<template>
  <div class="footer">
    <div class="container">
      <div class="footer__inner">
        <div class="social">
          <a href="#" class="social__item">
            <img src="../assets/images/facebook-icon.svg" alt="facebook" class="social-icon">
          </a>
          <a href="#" class="social__item">
            <img src="../assets/images/vk-icon.svg" alt="vkontakte" class="social-icon">
          </a>
          <a href="#" class="social__item">
            <img src="../assets/images/instagram-icon.svg" alt="instagram" class="social-icon">
          </a>
          <a href="#" class="social__item">
            <img src="../assets/images/twitter-icon.svg" alt="twitter" class="social-icon">
          </a>
          <a href="#" class="social__item">
            <img src="../assets/images/benance-icon.svg" alt="Benance" class="social-icon">
          </a>
        </div>
        <div class="footer__bottom">
          <a href="#" class="footer__politics">Политика конфиденциальности</a>
          <div class="copyright">
            <img src="../assets/images/copy-icon.svg" alt="copyright" class="copyright__icon">
            <p class="copyright__text">
              2021 <span class="copy">&copy;</span> Riverstart Digital. Все права защищены
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>  
</template>


<style lang="scss" scoped>
@import '../assets/styles/base.scss';

.footer {
  padding-top: 4.625rem;
  padding-bottom: 1.5rem;
  font-family: 'MabryPro', sans-serif;
  font-size: 0.75rem;
  line-height: 1.188rem;
  font-weight: 400;
  letter-spacing: 1%;
  color: $color-grey1;
  &__politics {
    color: $color-grey2;
  }
}
  .social {
    margin-bottom: 4.938rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .copyright {
    margin-top: 1.25rem;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    &__icon {
      margin-right: 8px;
    }
  }
  
  .copy {
    vertical-align: top;
  }
  
@media (min-width: 768px)  {
  .footer {
    padding-top: 6.5rem;
    padding-bottom: 2.563rem;
    &__inner {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: end;
    }
  }
  .social {
    order: 2;
    margin-bottom: 0;
    &__item {
      margin-left: 43px;
    }
  }
  .container {
    padding: 0 40px;
  }
}

@media (min-width: 1280px)  {
  .footer {
    padding-top: 81px;
    padding-bottom: 74px;
    &__inner {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: end;
    }
    &__bottom {
      display: flex;
      align-items: baseline;
      justify-content: flex-start;
    }
    &__politics {
      padding-bottom: 10px;
      order: 2;
    }
  }
  .copyright {
    margin-top: 0;
    align-items: baseline;
    margin-right: 34px;
  }
  .container {
    padding: 0 80px;
  }
}

@media (min-width: 1920px)  {
  .container {
    padding: 0 120px;
  }
  .footer {
    padding-top: 120px;
    padding-bottom: 112px;
  }
  .copyright {
      margin-right: 34px;
    }
    
  .social {
    &__item {
      margin-left: 70px;
    }
  }
  .social-icon {
    width: 18px;
    height: 18px;
  }
}

</style>
