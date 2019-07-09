<template>
  <main class="mainWrapper">
    <section class="contentWrapper">
      <div v-if="loaded" class="asset">
        <img src="~/assets/images/Group 1.svg" alt="pattern" />
      </div>
      <transition name="fade">
        <article v-if="loaded" class="content">
          <h1>Poznaj ręcznie robione zaproszenia</h1>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.</p>
          <hr />
          <div class="buttons">
            <button class="btn btn--primary">Zamów</button>
            <button class="btn btn--ghost">Oferta</button>
          </div>
        </article>
      </transition>
    </section>
    <section data-aos="fade-up" data-aos-duration="1000" class="whyIsWorthWrapper">
      <article class="whyIsWorthContent">
        <h2>Dlaczego Warto?</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
        <button class="btn btn--ghost">Oferta</button>
      </article>
      <aside class="whyIsWorthAssets">
        <div data-aos="fade-up" class="whyIsWorthAssets__item">
          <h3>oryginalność</h3>
          <p>Lorem ipsum dolo sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
        </div>
        <div data-aos="fade-up" class="whyIsWorthAssets__item">
          <h3>jakość</h3>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
        </div>
        <div data-aos="fade-up" class="whyIsWorthAssets__item">
          <h3>elegancja</h3>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
        </div>
      </aside>
    </section>
    <section data-aos="fade-up" data-aos-duration="1000" class="ofertWrapper">
      <h2>Oferta</h2>
      <article class="ofert__info">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
          <br />empor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
        </p>
      </article>
      <div class="ofert__items">
        <ofert-item :name="'Deep Blue'" :price="14" :colors="['blue','green']" />
        <ofert-item :name="'Deep gereben'" :price="104" :colors="['blue','green']" />
        <ofert-item :name="'Deep Blue'" :price="14" :colors="['blue','green']" />
      </div>
    </section>
    <section class="contactWrapper">
      <h2>Kontakt</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
        <br />ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
        <br />tur adipiscing elit, sed do eiusmod tempor incididunt u
      </p>
      <h3>
        kontakt@kaligrafowane.pl
        <br />‭tel. 512 914 465‬
      </h3>
    </section>
  </main>
</template>

<script>
import ofertItem from '../components/ofertItem'
import Separator from '../components/Separator'
export default {
  components: { ofertItem, Separator },
  data() {
    return {
      loaded: false
    }
  },
  mounted() {
    this.loaded = true
  }
}
</script>

<style lang="scss" scoped>
@import '~/assets/style/vars.scss';

.mainWrapper {
  position: relative;
}
//CTA section
.contentWrapper {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  height: 100vh;
  .asset {
    flex: 1;
    position: relative;
    img {
      position: absolute;
      left: -20%;
      top: -24vh;
      width: 100%;
      transform: scale(1);
      z-index: -99;
    }
  }
  .content {
    flex: 2;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: left;
    p {
      padding-bottom: 20px;
    }
    h1 {
      line-height: 1;
    }
  }
}
//whyisworth section
.whyIsWorthWrapper {
  display: flex;
  flex-direction: column;
  .whyIsWorthAssets {
    display: flex;
    flex-direction: column;
    margin: 5vh 0;
    .whyIsWorthAssets__item {
      &:nth-child(1) {
        border-left: 1.5px solid $blue;
      }
      &:nth-child(2) {
        border-left: 1.5px solid $rose;
      }
      &:nth-child(3) {
        border-left: 1.5px solid $gold;
      }
      display: flex;
      flex-direction: column;
      flex: 1;
      margin: 10px;
      padding: 15px;
      border-radius: $radius;
      p {
        font-size: $small;
      }
    }
  }
}

//ofert section
.ofertWrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  .ofert__info {
    text-align: center;
  }
  .ofert__items {
    margin: 7vh 0 5vh;
  }
}
.footerPattern {
  display: none;
}
//media queries
@media (min-width: 720px) {
  .contentWrapper {
    flex-direction: row;
    .asset > img {
      transform: scale(1.2);
      left: -5vw;
      top: -1.5vh;
    }
  }

  .whyIsWorthWrapper {
    flex-direction: row;
    padding: 100px;
    .whyIsWorthContent {
      flex: 1;
      padding: 20px;
    }
    .whyIsWorthAssets {
      flex-direction: row;
      flex: 1;
      .whyIsWorthAssets__item {
        color: #fff;
        display: flex;
        flex-direction: column;
        text-align: center;
        flex: 1;
        margin: 10px;
        padding: 15px;
        border-radius: $radius;
        height: 230px;
        &:nth-child(1) {
          background: $blue;
        }
        &:nth-child(2) {
          background: $rose;
          color: $blue;
          transform: translateY(-30px);
          h3 {
            color: $blue;
          }
        }
        &:nth-child(3) {
          background: $gold;
        }
        h3 {
          color: #fff;
        }
      }
    }
  }
  .ofertWrapper {
    padding: 0 100px;
  }
  .contactWrapper {
    padding: 100px;
    text-align: center;
  }
}
.footerPattern {
  position: absolute;
  display: block;
  width: 20%;
  right: -20px;
  bottom: -0;
}
</style>
