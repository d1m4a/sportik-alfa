<template lang="pug">
  b-container
      b-row
        b-col
          section.art__location
            h2.art__header Место номер {{ $route.params.id }}
            b-button(to="/locations/" pill).btn__back << Назад
</template>

<script>
export default {
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
</style>