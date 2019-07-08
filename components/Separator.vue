<template>
  <div class="sepeartorWarpper">
    <div class="firstLine"></div>
    <div class="secLine"></div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import '~/assets/style/vars.scss';

.sepeartorWarpper {
  width: 100vw;
  height: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.firstLine {
  width: 40px;
  height: 1px;
  background: $gold;
}
.secLine {
  width: 80px;
  height: 1px;
  background: $blue;
  margin-top: 10px;
}
</style>