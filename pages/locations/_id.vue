<template lang="pug">
  b-container
    b-row
      b-col
        b-card(no-body).overflow-hidden.mb30
          b-row(no-gutters)
            b-col(md="4")
              b-card-img(src="https://picsum.photos/400/400/?image=20").rounded-0

            b-col(md="8")
              b-card-body(:title=`namePlace + $route.params.id` )
                b-card-text This is a wider card with supporting text as a natural lead-in to additional content.
        div.text-center
          b-button(to="/locations/" variant="outline-dark").btn__back << Назад
</template>

<script>
export default {
  data: function () {
    return {
      namePlace: 'Место номер #'
    }
  },
  validate({params}) {
    return /^\d+$/.test(params.id)
  }
}
</script>

<style lang="scss">
.btn__back{
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
  }
  .mb30{
    margin-bottom: 30px;
  }
</style>