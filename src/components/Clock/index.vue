<template>
  <section>
    <div class="clock">
      <div id="hour" class="hand hours"></div>
      <div id="minute" class="hand minutes"></div>
      <div id="second" class="hand seconds"></div>
      <template v-for="index in 12">
        <div class="number" :class="`number${index}`">{{ index }}</div>
      </template>
    </div>
  </section>
</template>

<script>
export default {
  name: "funnyVueClock",
  created() {
    this.timer = setInterval(this.setClock, 1000)
  },
  beforeDestroy() {
    clearInterval(this.timer)
  },
  methods: {
    setRotation(element, rotation) {
      element.style.setProperty(`--rotate`, rotation);
    },
    setClock() {
      const hour = document.getElementById("hour")
      const minute = document.getElementById("minute")
      const second = document.getElementById("second")
      const day = new Date()
      const h = day.getHours()
      const m = day.getMinutes()
      const s = day.getSeconds()
      const hourDegree = (h * 30) + (m * 0.5)
      const minuteDegree = (m * 6) + (s * 0.1)
      const secondDegree = (s * 6)

      this.setRotation(second, secondDegree)
      this.setRotation(minute, minuteDegree)
      this.setRotation(hour, hourDegree)
    }
  }
}
</script>

<style lang="scss" scoped>
section {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 80vh;
  overflow: hidden;

  .clock {
    position: relative;
    width: 400px;
    height: 400px;
    border-radius: 50%;
    border: 12px solid #180909;
    background-image: linear-gradient(90deg, #E2CB9A 6%, #F0D595 48%, #D5C08A 100%);
    box-shadow: inset -20px 1px 52px 0 rgba(37, 24, 7, 0.13), inset 48px 17px 100px 0 rgba(52, 28, 0, 0.91);


    .number {
      --rotate: 0;
      position: absolute;
      width: 100%;
      height: 100%;
      text-align: center;
      transform: rotate(var(--rotate));
      font-size: 1.8rem;
      font-weight: 500;
    }

    &::before {
      // content: "";
      position: absolute;
      width: calc(100% - 16px);
      height: calc(100% - 16px);
      border-radius: 50%;
      left: 8px;
      top: 8px;
      background-image: linear-gradient(90deg, #E2CB9A 6%, #F0D595 48%, #D5C08A 100%);
      box-shadow: inset -20px 1px 52px 0 rgba(37, 24, 7, 0.13), inset 48px 17px 100px 0 rgba(52, 28, 0, 0.91);
    }

    &::after {
      content: "";
      position: absolute;
      left: 50%;
      bottom: 50%;
      width: 14px;
      height: 14px;
      background-color: black;
      border-radius: 50%;
      z-index: 12;
      transform: translate(-50%, 50%);
    }

    .number1 {
      --rotate: 30deg;
    }

    .number2 {
      --rotate: 60deg;
    }

    .number3 {
      --rotate: 90deg;
    }

    .number4 {
      --rotate: 120deg;
    }

    .number5 {
      --rotate: 150deg;
    }

    .number6 {
      --rotate: 180deg;
    }

    .number7 {
      --rotate: 210deg;
    }

    .number8 {
      --rotate: 240deg;
    }

    .number9 {
      --rotate: 270deg;
    }

    .number10 {
      --rotate: 300deg;
    }

    .number11 {
      --rotate: 330deg;
    }

    .hand {
      --rotate: 0;
      position: absolute;
      left: 50%;
      bottom: 50%;
      transform-origin: bottom;
      border-radius: 10px;
      z-index: 10;
      transform: translateX(-50%) rotate(calc(var(--rotate) * 1deg));
    }

    .seconds {
      width: 2px;
      height: 45%;
      background-color: rgb(155, 10, 10);
      z-index: 11;
    }

    .minutes {
      width: 6px;
      height: 36%;
      background-color: rgb(25, 38, 133);
      z-index: 10;
    }

    .hours {
      width: 12px;
      height: 30%;
      background-color: black;
      z-index: 9;
    }

  }
}


</style>
