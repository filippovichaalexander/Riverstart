<script setup>

</script>

<template>
  <div class="contacts">
    <div class="contacts__container">
      <div class="contacts__inner">
        <div class="contacts__top">
          <div class="contacts__item">
            <p class="contacts__city color--white">Московский офис</p>
            <p class="contacts__bottom-item color--grey">
              Новая пл., 6
            </p>
            <p class="contacts__bottom-item color--grey">
              8 (499) 112-46-21
            </p>
          </div>
          <div class="contacts__item">
            <p class="contacts__city color--white">Нижегородский офис</p>
            <p class="contacts__bottom-item color--grey">
              ул. Рождественская, 26
            </p>
            <p class="contacts__bottom-item color--grey">
              8 (831) 2-889-354
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="contacts__middle">
      <div class="container--middle">
        <div class="contacts__item">
          <p class="contacts__city color--white">Таллинский офис</p>
            <p class="contacts__bottom-item color--grey">
              3 korrus, Metro Plaza, Viru väljak 2
            </p>
            <p class="contacts__bottom-item color--grey">
              +372 610-42-53
            </p>
          </div>
          <div class="contacts__middle-bottom">
            <div class="contacts__middle-bottom-content">
              <div class="contacts__middle-bottom-content-top color--grey">
                <p class="contacts__middle-bottom-content-inner">
                  Oceanstart LLC
                </p>
                <p class="contacts__middle-bottom-content-inner">
                  Worldwide outsourcing and outstaffing
                </p>
              </div>
              <div class="contacts__middle-bottom-link-wrapper">
                <p class="contacts__middle-bottom-link-text color--white">oceanstart.dev</p>
                <img src="../assets/images/ocean-art-link.svg" alt="link" class="contacts__middle-bottom-link-icon" />
              </div>
            </div>
            <div class="contacts__middle-bottom-icon-wrapper">
              <img src="../assets/images/ocean-logo.svg" alt="ocean art" class="contacts__middle-bottom-icon">
            </div>
          </div>

      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '../assets/styles/base.scss';


.color--white {
  color: $white;
}
.color--grey {
  color: rgba(247, 247, 250, 0.5);
}
.contacts {
  
  padding: 36px 0 24px 0;
  
  font-family: 'MabryPro', sans-serif;
  font-size: 0.75rem;
  font-weight: 400;
  line-height: 0.9rem;
  letter-spacing: 1%;
  &__top {
    padding: 2.25rem 0 2.625rem 0;
    
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__bottom-item:nth-child(2) {
      margin: 0.625rem 0 0.625rem 0;
  }
  &__middle {
    padding: 1.375rem 0 1.375rem 0;
    background-color: rgba(247, 247, 250, 5%);
  }
  &__middle-bottom {
    margin-top: 48px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__middle-bottom-content-top {
    margin-bottom: 1.10rem;
  }
  &__middle-bottom-content-inner {
    line-height: 1.3;
  }
  &__middle-bottom-link-wrapper {
    display: flex;
    align-items: baseline;
    justify-content: flex-start;
  }
  &__middle-bottom-link-text {
    margin-right: 5px;
    font-size: 0.938rem;
    line-height: 1.125rem;
    font-weight: 400;
  }
  &__middle-bottom-icon-wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-radius: 50%;
    width: 59px;
    height: 59px;
    min-width: 59px;
    min-height: 59px;
    background-color: $color-grey2;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
@media (min-width: 768px)  {
  .contacts {
    padding-top: 48px;
    padding-bottom: 0;
    &__top {
      padding-top: 0;
      justify-content: flex-start;
    }
    &__item:nth-child(1) {
      margin-right: 140px;
    }
    &__middle {
      border-radius: 20px;
      margin-right: 40px;
      margin-left: 40px;
    }
  }
}
@media (min-width: 1280px)  {
  .container {
    &--middle {
      padding: 22px 22px 23px 26px;
    }
  }
  .contacts {
    padding-top: 0;
    padding-bottom: 0;
    &__top {
      padding-top: 0;
      justify-content: flex-start;
    }
    &__item:nth-child(1) {
      margin-right: 140px;
    }
    &__middle {
      margin-right: 80px;
      margin-left: 80px;
    }
  }
}

@media (min-width: 1920px)  {
  .contacts {
    font-size: 18px;
    &__top {
      padding-bottom: 64px;
    }
    &__middle {
      margin: 0;
    }
    &__item:nth-child(1) {
      margin-right: 83px;
    }
    &__container {
      &--middle {
        padding: 33px 33px 33px 39px;
      }
    }
    &__bottom-item:nth-child(2) {
        margin: 15px 0;
    }
    &__middle-bottom-link-text {
      margin-top: 29px;
      font-size: 23px;
    }
    &__middle-bottom-icon-wrapper {
      width: 90px;
      height: 90px;
    }
    &__middle-bottom-icon {
      height: 23px;
    }
  }
}
</style>