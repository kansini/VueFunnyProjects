<template>
  <div class="home">
    <vue-calculator />
  </div>
</template>

<script>
import vueClock from '@/components/Clock'
import vueCalculator from '@/components/Calculator'
export default {
  name: 'Home',
  components: {
    vueClock,
    vueCalculator
  }
}
</script>
