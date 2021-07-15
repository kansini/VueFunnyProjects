<template>
  <div class="home">
    <v-clock />
  </div>
</template>

<script>
import vClock from '@/components/Clock'
import vCalculator from '@/components/Calculator'
export default {
  name: 'Home',
  components: {
    vClock,
    vCalculator
  }
}
</script>
