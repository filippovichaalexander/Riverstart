<template>
  <div class="projects">
    <div class="projects__container">
      <div class="projects__inner">
        <h2 class="projects__title">Обсудить проект</h2>
        <p class="projects__text">Расскажите о проекте в форме ниже <br> или свяжитесь с нами напрямую </p>
        <div class="projects__info-wrapper">
          <div class="projects__info projects--info1">
            <p class="projects__email">hello@riverstart.ru</p>
            <a href="" class="projects__feedback">Написать нам на почту</a>
          </div>
          <div class="projects__info projects--info2">
            <div class="projects--info2-top">
              <p class="projects__email">@ekhohrin</p>
              <div class="projects__email-icon-wrapper">
                <img 
                  src="../assets/images/person-director-icon2.svg" 
                  alt="director" 
                  class="projects__email-icon">
              </div>
            </div>
            <a href="" class="projects__feedback">Написать нашему аккаунт-директору в Telegram</a>
          </div>  
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
@import '../assets/styles/base.scss';
.projects {
  margin-top: 87px;
  font-family: 'MabryPro', sans-serif;
  background-color: $color-background2;
  color: $white;
  font-weight: 400;
  &__title {
    font-size: 2.375rem;
    line-height: 2.813rem;
    margin-bottom: 1rem;
  }
  &__text {
    font-size: 1rem;
    line-height: 1.5rem;

    margin-bottom: 3.688rem;
  }
  &__info-wrapper {
    display: flex;
    flex-direction: column;
    align-items: left;
    justify-content: flex-start;
  }
  
  &--info1 {
    margin-bottom: 21px;
  }
  &--info2 {
    margin-bottom: 45px;
  }
  &--info2-top {
    display: flex;
    align-items: center;
    justify-content: flex-start;
  }
  &__email {
    margin-right: 8px;
    font-size: 1.5rem;
    line-height: 1.625rem;
  }
  &__email-icon-wrapper {
    width: 30px;
    height: 30px;
    border-radius: 6px;

    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }
  &__feedback {
    font-size: 0.75rem;
    line-height: 1.188rem;
    color: rgba(247, 247, 250, 60%);

  }
}
@media (min-width: 768px)  {
  .projects {
    &__info-wrapper {
      flex-direction: row;
      justify-content: flex-start;
    }
    &__email-icon-wrapper {
      order: 1;
    }
    &__email:nth-child(2) {
      order: 2;
      margin-right: 0;
      margin-left: 8px;
    }
    &__info-wrapper {
      flex-direction: column;
    }
  }
  .projects--info1 {
    margin-right: 131px;
  }
}

@media (min-width: 1280px)  {
  .projects {
    &__title {
      padding-bottom: 36px;
      font-size: 3.5rem;
      white-space: nowrap;
    }
    &--info1 {
      margin-right: 0;
      margin-bottom: 42px;
    }
    &--info2 {
      margin-bottom: 130px;
    }
    &__text {
      margin-bottom: 114px;
    }
    &__title {
      margin-bottom: 36px;
    }
  }
}

@media (min-width: 1920px)  {
  .projects {
    &__title {
      font-size: 85px;
      white-space: nowrap;
      padding-bottom: 52px;
    }
    &__text {
      margin-bottom: 168px;
      font-size: 26px;
      line-height: 41px;
    }
    &__email {
      margin-bottom: 14px;
      font-size: 42px;
      line-height: 46px;
    }
    &__feedback {
      font-size: 18px;
    }
    &--info1 {
      margin-bottom: 66px;
    }
    &--info2 {
      margin-bottom: 195px;
    }
  }
}
</style>