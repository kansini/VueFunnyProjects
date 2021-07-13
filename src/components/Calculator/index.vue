<template>
  <div class="calculator-container">
    <div class="header">
      <div class="logo"></div>
      <div class="solar-panel">
        <div class="division" v-for="index in 3"></div>
      </div>
    </div>
    <div class="display"></div>
  </div>
</template>

<script>
export default {
  name: "funnyVueCalculator"
}
</script>

<style lang="scss" scoped>
.calculator-container {
  width: 300px;
  height: 506px;
  padding: 12px 8px;
  border-radius: 8px;
  background: #D7D8DB;
  box-shadow: 0 0 23px 0 rgba(0, 0, 0, 0.09), 1px 2px 3px 0 rgba(0, 0, 0, 0.05), 1px 0 8px 0 rgba(0, 0, 0, 0.39), 1px 0 1px 0 rgba(0, 0, 0, 0.40), inset -2px 0 5px 0 rgba(0, 0, 0, 0.36), inset -5px 0 10px 0 rgba(209, 212, 214, 0.27), inset 0 1px 3px 0 rgba(0, 0, 0, 0.37), inset -7px 0 12px 0 rgba(161, 164, 169, 0.21), inset 0 5px 5px 0 rgba(255, 255, 255, 0.15), inset 6px 0 2px 0 rgba(255, 255, 255, 0.52);

  .header {
    position: relative;
    width: 100%;
    height: 64px;

    .solar-panel {
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      position: absolute;
      top: 8px;
      right: 16px;
      width: 128px;
      height: 44px;
      background-image: linear-gradient(180deg, #A4A39F 0%, #B8B7B2 47%, #CAC9C6 100%);
      border: 1px solid rgba(184, 183, 178, 0.41);
      box-shadow: inset 0 -1px 0 0 rgba(0, 0, 0, 0.03), inset 0 1px 0 0 rgba(76, 46, 46, 0.17), inset 0 1px 3px 0 rgba(0, 0, 0, 0.16), inset -1px 0 0 0 rgba(255, 255, 255, 0.50), inset 1px 0 0 0 rgba(45, 0, 0, 0.82), inset 0 -2px 0 0 rgba(185, 183, 175, 0.28), inset 0 -1px 4px 0 rgba(255, 255, 255, 0.37), inset -1px 0 2px 0 rgba(255, 255, 255, 0.31);
      border-radius: 5px;

      &::before {
        content: '';
        position: absolute;
        top: 2px;
        right: 2px;
        bottom: 2px;
        left: 2px;
        background: rgba(108, 103, 98, 0.97);
        border: 1px solid rgba(45, 36, 26, 0.06);
        box-shadow: inset 1px 1px 3px 0 rgba(0, 0, 0, 0.50), inset 3px 1px 3px 0 rgba(35, 18, 6, 0.50);
        border-radius: 3px;
      }

      .division {
        width: 2px;
        height: calc(100% - 4px);
        opacity: .5;
        background: #767068;
        z-index: 999;
      }
    }

  }

  .display {
    width: 100%;
    height: 128px;
    border-radius: 12px;
    padding: 12px 12px 16px 12px;
    background: #222328;
    box-shadow: 1px 0 1px 0 rgba(255, 255, 255, 0.56), 0 1px 1px 0 rgba(255, 255, 255, 0.11), inset 0 -13px 24px 0 rgba(205, 205, 205, 0.26), inset 0 -1px 3px 0 rgba(0, 0, 0, 0.18), inset 1px 0 1px 0 rgba(0, 0, 0, 0.17), inset 2px 0 3px 0 rgba(0, 0, 0, 0.31), inset 0 1px 1px 0 rgba(0, 0, 0, 0.28);

    &::before {
      display: block;
      content: '';
      width: 100%;
      height: 100%;
      background-image: linear-gradient(180deg, #6E9EA2 0%, #7EA7AA 49%, #83B2B6 100%);
      box-shadow: inset -1px 0 0 0 rgba(0, 0, 0, 0.14), inset 1px 0 0 0 rgba(0, 0, 0, 0.15), inset 5px 0 6px 0 rgba(46, 58, 48, 0.60), inset 0 1px 1px 0 rgba(0, 0, 0, 0.08), inset 0 3px 4px 0 rgba(5, 19, 6, 0.36);
      border-radius: 4px;
    }
  }
}
</style>
