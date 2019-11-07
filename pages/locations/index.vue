<template lang="pug">
  section.wrapper
    b-container(fluid)
      b-row
        b-col
          h2.header__places Места для занятий спортом
          b-card-group
            b-card( 
              v-for="location in locations"
              :key="location.id"
              bg-variant="dark"
              text-variant="white"
              :title="location.title"
              :img-src="location.imgSrc"
              :img-alt="location.title"
              img-top
              tag="article"
              class="mb-2 text-center card__item"
            )
              b-card-text {{ location.descr }}
              b-button(to="#" pill @click.prevent="showLocation(location)").btn__view Посмотреть
</template>

<script>
export default {
  data: ()=> ({
    locations: [
      { id: 1,
        title: 'место первое',
        imgSrc: 'https://picsum.photos/600/300/?image=10',
        descr: 'Описание первого места' },
      { id: 2,
        title: 'место второе',
        imgSrc: 'https://picsum.photos/600/300/?image=11',
        descr: 'Описание второго места' },
      { id: 3,
        title: 'место третье',
        imgSrc: 'https://picsum.photos/600/300/?image=12',
        descr: 'Описание третьего места' },
      { id: 4,
        title: 'место четвертое',
        imgSrc: 'https://picsum.photos/600/300/?image=13',
        descr: 'Описание четвертого места' },
      { id: 5,
        title: 'место пятое',
        imgSrc: 'https://picsum.photos/600/300/?image=14',
        descr: 'Описание пятого места' },
      { id: 6,
        title: 'место шестое',
        imgSrc: 'https://picsum.photos/600/300/?image=15',
        descr: 'Описание шестого места' },
      { id: 7,
        title: 'место седьмое',
        imgSrc: 'https://picsum.photos/600/300/?image=16',
        descr: 'Описание седьмого места' }
    ]
  }),
  methods:{
    showLocation(location) {
      this.$router.push('/locations/' + location.id)
    }
  }
}
</script>

<style lang="scss">
  .card__item{
    min-width: 270px;
    max-width: 300px;
    margin-right: 10px;
  }
  .card__item:last-child{
    margin-right: 0;
  }
  .btn__view{
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
  }
  .card-title{
    text-transform: uppercase;
    color: #FF3366;
  }
</style>