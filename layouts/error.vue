<template lang="pug">
  b-container
      b-row
        b-col
          h1.error.text-center Ты кажется не туда зашел!?
          div.mb30
            b-img(b-img center src="~assets/img/idontknow.png" alt="i don't know")
          h3.error.text-center Возвращайся-ка ты домой!
          div.text-center
            b-button(to="/" variant="outline-secondary").text-bold Вернуться домой
</template>

<style lang="scss">
  .error{
    margin-bottom: 50px;
    font-family: 'Roboto Condensed', sans-serif;
  }
  .mb30{
    margin-bottom: 30px;
  }
  .text-bold{
    font-weight: bold !important;
    text-transform: uppercase;
  }
</style>