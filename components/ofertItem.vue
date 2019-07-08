<template>
  <article class="ofert__item">
    <img src="#" alt="zdjęcie zaproszenia" />
    <div class="item__info">
      <h3>{{this.newName}}</h3>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliqui
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididun.
      </p>
      <h4>{{this.newPrice}}PLN/SZT</h4>
      <div class="colors">
        <div class="colors__item"></div>
        <div class="colors__item"></div>
        <div class="colors__item"></div>
      </div>
      <div class="buttons">
        <button class="btn btn--primary">Zamów</button>
        <button class="btn btn--ghost">Zapytaj</button>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  data() {
    return {
      newName: null,
      newPrice: null,
      newColors: []
    }
  },
  props: ['name', 'price', 'colors'],
  mounted() {
    this.newName = this.name
    this.newPrice = this.price
    this.newColors = this.colors
  }
}
</script>

<style lang="scss" scoped>
@import '~/assets/style/vars.scss';
//ofert sectioan
.ofert__item {
  margin-top: 5vh;
  display: flex;
  flex-direction: column;
  img {
    background: rgb(46, 53, 81);
    background: linear-gradient(
      45deg,
      rgba(46, 53, 81, 1) 0%,
      rgba(216, 173, 131, 1) 100%
    );
    border: 0;
    border-radius: $radius;
    width: 100%;
    height: 30vh;
  }
  .colors {
    width: 100%;
    display: flex;
    .colors__item {
      padding: 10px;
      height: 30px;
      width: 30px;
      margin: 0 10px;
      border-radius: 100%;
      &:nth-child(1) {
        background: $blue;
      }
      &:nth-child(2) {
        background: $rose;
      }
      &:nth-child(3) {
        background: $gold;
      }
    }
  }
}
//media queries
@media (min-width: 720px) {
  .ofert__item {
    flex-direction: row;
    position: relative;
    align-items: center;
    img {
    }
    .item__info {
      display: flex;
      flex-direction: column;
      padding: 20px;
    }
  }
}
</style>