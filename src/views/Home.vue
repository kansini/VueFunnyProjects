<template>
  <div class="home">
    <vue-radio />
  </div>
</template>

<script>
import vueClock from '@/components/Clock'
import vueCalculator from '@/components/Calculator'
import vueRadio from '@/components/Radio'
export default {
  name: 'Home',
  components: {
    vueClock,
    vueCalculator,
    vueRadio
  }
}
</script>
