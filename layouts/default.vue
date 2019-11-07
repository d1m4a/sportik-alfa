<template lang="pug">
div
  section.page__content.mb50
    navi
    nuxt
  foot

</template>

<script>
import Navi from '@/components/Navi'
import Foot from '@/components/Foot'

export default {
  components: {
    Navi,
    Foot
  }
}
</script>

<style lang="scss">
.mb50{
  margin-bottom: 50px;
}
</style>