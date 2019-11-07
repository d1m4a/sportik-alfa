<template lang="pug">
  main
    b-container
      b-row
        b-col
          h1.header__places Добро пожаловать на сервис "Sportik" 
            sup.sup alfa
          Carousel

</template>

<script>
import Carousel from '@/components/Carousel'
export default {
  components:{
    Carousel
  }
}
</script>

<style lang="scss">
.sup{
  color: #FF3366;
}
</style>
