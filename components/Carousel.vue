<template lang="pug">
  b-carousel(
    id="carousel-1"
    v-model="slide"
    :interval="4000"
    controls
    indicators
    background="#ababab"
    img-width="700"
    img-height="250"
    style="text-shadow: 1px 1px 2px #333;"
    @sliding-start="onSlideStart"
    @sliding-end="onSlideEnd")

    b-carousel-slide(
      caption="ШАГ ПЕРВЫЙ"
      text="ВЫБЕРИТЕ МЕСТО ДЛЯ ЗАНЯТИЙ ИЗ СПИСКА ЛОКАЦИЙ"
      img-src="https://picsum.photos/700/250/?image=52")

    b-carousel-slide(
      caption="ШАГ ВТОРОЙ"
      text="НОГИ В РУКИ И БЕГОМ ТУДА ЗАНИМАТЬСЯ СПОРТОМ."
      img-src="https://picsum.photos/700/250/?image=54")

    b-carousel-slide(
      caption="ШАГ ТРЕТИЙ"
      text="PROFIT. КРАСАВЧИК!"
      img-src="https://picsum.photos/700/250/?image=60")

</template>

<script>
export default {
    data() {
      return {
        slide: 0,
        sliding: null
      }
    },
    methods: {
      onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      }
    }
  }
</script>

<style lang="scss">
.carousel-caption{
  background-color: rgba(255, 255, 255, 0.7);
  right: 0;
  left: 0;
  bottom: 50px;
  padding-top: 20px;
  padding-bottom: 20px;
}
.carousel-caption h3{
  font-family: 'Open Sans Condensed', sans-serif;
  font-weight: bold !important;
  color: #FF3366;
  text-shadow: 1px 1px 2px #777;
}
.carousel-caption p{
  font-family: 'Open Sans Condensed', sans-serif;
  font-weight: bold;
  margin-bottom:0 !important;
  color: #343a40;
  text-shadow: 1px 1px 2px #999;
}
</style>