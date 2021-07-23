<template>
  <section>
    <div class="radio-body">
      <div class="radio-speaker">
        <div class="dot" v-for="index in 121"></div>
      </div>
      <div class="radio-knob">
        <div class="radio-knob-inner"></div>
        <div class="radio-knob-indicator--left"></div>
        <div class="radio-knob-indicator--right"></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "funnyVueRadio"
}
</script>

<style lang="scss" scoped>
section {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-image: linear-gradient(180deg, #EEECEA 0%, #ECEAE8 22%, #DCDAD8 71%, #E8E6E4 74%, #FFFDFB 97%);

  .radio-body {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    width: 212px;
    height: 382px;
    border-radius: 8px;
    overflow: hidden;

    &::before {
      position: absolute;
      content: '';
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      transform: scaleX(-1);
      background-image: linear-gradient(216deg, #F3EEEA 0%, #E7E6DC 100%);
      box-shadow: 0 -1px 1px 0 rgba(216, 209, 195, 0.60), 0 0 0 0 rgba(148, 133, 104, 0.20), 0 2px 25px 0 rgba(0, 0, 0, 0.06), inset 0 -3px 5px 0 rgba(188, 182, 173, 0.50), inset 0 -2px 3px 0 #B3B0A9, inset -5px 5px 4px 0 rgba(255, 255, 255, 0.70), inset 3px 1px 3px 0 rgba(207, 202, 194, 0.80), inset 6px 6px 3px 0 #EFEDE8;
      z-index: 0;
    }

    .radio-speaker {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      width: 178px;
      margin: 24px auto;

      .dot {
        position: relative;
        width: 8px;
        height: 8px;
        margin-bottom: 8px;
        border-radius: 4px;

        &::before {
          position: absolute;
          content: '';
          left: 0;
          top: 0;
          width: 8px;
          height: 8px;
          margin-bottom: 8px;
          border-radius: 4px;
          background: #865F43;
          box-shadow: 0 0 1px 1px rgba(255, 255, 255, 0.90), inset 0 -1px 0 0 rgba(0, 0, 0, 0.30), inset 0 2px 1px 0 rgba(0, 0, 0, 0.50);
          z-index: 999;
        }

        &:not(:nth-child(11n+11)) {
          margin-right: 8px;
        }
      }
    }

    .radio-knob {
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      width: 128px;
      height: 128px;
      border-radius: 50%;
      background: #EDEAE5;
      border: 2px solid #8E8C8D;
      box-shadow: 0 1px 2px 0 rgba(255, 255, 255, 0.80);
      z-index: 999;

      &::before {
        content: '';
        position: absolute;
        top: 2px;
        right: 2px;
        bottom: 2px;
        left: 2px;
        border-radius: 50%;
        background: #EDEAE5;
        box-shadow: inset 0 1px 2px 0 #FFFFFF;
      }
    }

    .radio-knob-inner {
      position: relative;
      width: 64px;
      height: 64px;
      border-radius: 50%;
      background: #EDEAE5;
      border: 2px solid #8E8C8D;
      box-shadow: 0 1px 2px 0 rgba(255, 255, 255, 0.80);
      z-index: 999;

      &::before,
      &::after {
        content: '';
        position: absolute;
        width: 8px;
        height: 8px;
        border-radius: 4px;
        background: #4E4037;
        box-shadow: 0 0 0 1px rgba(255, 255, 255, 0.60), inset 0 0 0 1px rgba(0, 0, 0, 0.40);
      }

      &::before {
        top: 12px;
        right: 16px;
      }

      &::after {
        bottom: 12px;
        left: 16px;
      }
    }

    [class^="radio-knob-indicator--"] {
      position: absolute;
      transform: rotate(-30deg);
      width: 16px;
      height: 3px;
      bottom: 24px;
      background: #F1F4F7;
      box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.20), 0 0 1px 1px rgba(0, 0, 0, 0.20), inset 0 0 1px 0 rgba(0, 0, 0, 0.60);
      border-radius: 40px;
    }

    .radio-knob-indicator--left {
      transform: rotate(-40deg);
      left: 14px;

    }

    .radio-knob-indicator--right {
      transform: rotate(-140deg);
      right: 14px;
    }
  }
}
</style>