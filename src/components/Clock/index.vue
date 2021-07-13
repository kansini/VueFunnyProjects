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
  beforeCreate() {
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
      const hh = day.getHours()
      const mm = day.getMinutes()
      const ss = day.getSeconds()
      const hourDegree = (hh * 30) + (mm * 0.5)
      const minuteDegree = (mm * 6) + (ss * 0.1)
      const secondDegree = (ss * 6)

      this.setRotation(second, secondDegree)
      this.setRotation(minute, minuteDegree)
      this.setRotation(hour, hourDegree)
    }
  }
}
</script>

<style lang="scss" scoped>
section {
  /* box-sizing: border-box; */
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 80vh;
  overflow: hidden;
}

.clock {
  width: 310px;
  height: 310px;
  background-color: rgba(255, 255, 255, 0.9);
  border-radius: 50%;
  border: 10px solid rgb(255, 255, 255);
  position: absolute;

  .number {
    /* color:rgb(224, 224, 224); */
    --rotate: 0;
    position: absolute;
    width: 100%;
    height: 100%;
    text-align: center;
    /* background-color: salmon; */
    transform: rotate(var(--rotate));
    font-size: 1.8rem;
    font-weight: 500;
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
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
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

</style>
