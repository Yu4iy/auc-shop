<template>
<div id="root">
  <Header/>
  <Hero/>
</div>
</template>

<script>

import Header from '@/components/Header.vue'
import Hero from '@/components/Hero.vue'
export default {
  name: 'App',
  components: {
    Header,
    Hero
  }
}
</script>

<style lang="scss">

</style>
