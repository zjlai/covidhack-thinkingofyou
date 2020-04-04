<template>
  <div class="fullscreen fit bg-image">
    <q-img src="~assets/background.jpg" />
  </div>
</template>

<script>
export default {
  name: 'backgroundImage',
  data () {
    return {}
  }
}
</script>
<style scoped>
.bg-image {
  z-index: -1
}
</style>
