<template>
  <div class="portfolio">
    <div class="products">
      <div class="image" v-for="product in products" :key="product.name">
        <a :href="product.src" target="_blank">
          <img :src="product.image" :alt="product.name">
        </a>
        <h3>{{ product.description }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      products: [
        {
          name: "karaokediary",
          src: "https://karaoke-diary.herokuapp.com/",
          image: require("@/assets/karaokediary.png"),
          description: "KARAOKE DIARY ( Laravel + Vue + Bulma )"
        },
        {
          name: "portfolio",
          src: "https://chachamame.com/",
          image: require("@/assets/portfolio.png"),
          description: "This Portfolio( Vue.js )"
        },
        {
          name: "BomberGame",
          src: "https://chachamame.github.io/BomberGame/",
          image: require("@/assets/BomberGame.png"),
          description: "ボンバーマン風( Vue.js )"
        },
        {
          name: "canvasBreakOut",
          src: "https://chachamame.github.io/BlockBall/",
          image: require("@/assets/canvasBreakOut.png"),
          description: "ブロック崩し( Canvas )"
        },
        {
          name: "nxnPuzzle",
          src: "https://chachamame-nxnpuzzle.netlify.com/",
          image: require("@/assets/nxnPuzzle.png"),
          description: "NxNパズル( Vue.js )"
        },
        {
          name: "p5BreakOut",
          src: "https://chachamame.github.io/p5breakout/",
          image: require("@/assets/p5BreakOut.png"),
          description: "ブロック崩し( p5.js )"
        },
        {
          name: "PascalsTriangle",
          src: "https://chachamame.github.io/PascalsTriangle/",
          image: require("@/assets/PascalsTriangle.png"),
          description: "パスカルの三角形( p5.js )"
        },
        {
          name: "SierpinskiGasket",
          src: "https://chachamame.github.io/SierpinskiGasket/",
          image: require("@/assets/SierpinskiGasket.png"),
          description: "シェルピンスキーのギャスケット( p5.js )"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.products {
  margin-top: 40px;
  display: grid;
  width: 60%;
  margin-left: 20%;
  margin-right: 20%;
  grid-template-rows: 300px 300px 300px 300px;
  grid-template-columns: 50% 50%;
}

@media screen and( max-width: 1400px  ) {
  .products {
    width: 80%;
    margin-left: 10%;
    margin-right: 10%;
  }
}

@media screen and( max-width: 480px) {
  .products {
    grid-template-columns: 100%;
    width: 100%;
    margin-left: 0;
    margin-right: 0;
  }

  .image h3 {
    transform: translateY(-100%);
  }
}

.image {
  position: relative;
  overflow: hidden;
  max-height: 100%;
}

.image a {
  display: block;
  height: 100%;
}

.image:hover h3 {
  transform: translateY(0px);
}

.image h3 {
  position: absolute;
  transform: translateY(100%);
  left: 0;
  right: 0;
  bottom: 0;
  transition: 0.5s;
  margin: 0 auto;
  text-align: center;
  background: rgba(0, 0, 0, 0.75);
  color: white;
  padding-top: 1rem;
  padding-bottom: 1rem;
  box-sizing: border-box;
}

.image img {
  // max-width: 100%;
  // max-height: 100%;
  width: 100%;
  height: 100%;
  object-fit: contain;
}
</style>
