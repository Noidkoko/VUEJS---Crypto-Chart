<template>
  <div class="container">
    <div
      :id="index"
      v-on:click="toggleModale"
      class="crypto-item"
      v-for="(crypto, index) in info"
      :key="crypto"
    >
      <p><img width="30" :src="crypto.image" /></p>
      <p>{{ crypto.name }}</p>
      <p>{{ crypto.current_price }}</p>
    </div>
    <div class="modale-container" v-if="revele == true">
      <div class="overlay"></div>
      <div v-on:click="toggleModale" class="modale">
        <p class="title">Infos cryptos</p>
        <div class="crypto-infos">
          <div class="top"><div class="line"><img class="img_modale" width="60" :src="info[id].image" /></div>
                            <div class="line"><p class="infos crypto-name">{{ info[id].name }}</p></div>
          </div>
          <div class="line">Prix actuel :<p class="infos">{{ info[id].current_price }}</p></div>
          <div class="line">Top 24h :<p class="infos">{{ info[id].high_24h }}</p></div>
          <div class="line">Bottom 24h :<p class="infos">{{ info[id].low_24h }}</p></div>
          <div class="line">G/P 24h (en %)<p class="infos">{{ info[id].price_change_24h }}</p></div>
        </div>
        <button class="close-modale">X</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "mainContainer",
  props: ["info"],
  data() {
    return {
      revele: false,
      id: null,
    };
  },
  methods: {
    toggleModale: function (e) {
      this.revele = !this.revele;
      return (this.id = e.target.id);
    },
  },
};
</script>

<style>
.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px;
}
.crypto-item {
  width: 200px;
  height: 130px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 15px;
  background-color: rgba(255, 255, 255, 0.089);
}
.crypto-item:hover {
  background-color: rgba(255, 255, 255, 0.301);
}
.crypto-item p {
  margin: 0;
}
.crypto-item img {
  margin: 0;
}
/* Modale */
.modale-container {
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  position: fixed;
  display: flex;
  justify-content: center;
  align-items: center;
}
.overlay {
  height: 100vh;
  width: 100vw;
  background-color: rgba(51, 51, 51, 0.664);
  position: absolute;
}
.modale {
  position: relative;
  margin: auto;
  height: 600px;
  width: 500px;
  border-radius: 20px;
  overflow: hidden;
  background-color: #2c3e50;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.modale .title {
  background-color: crimson;
  position: absolute;
  top: 0;
  padding: 15px;
  margin: 0;
  width: 100%;
}
button {
  bottom: 0;
  left: 0;
  position: absolute;
  width: 100%;
  height: 6vh;
  background-color: crimson;
  border: none;
  outline: none;
  font-weight: bold;
  font-size: 22px;
  color: white;
}
button:hover {
  font-size: 26px;
}
.modale div {
  color: black;
}
.crypto-infos {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

}
.infos {
  background-color: rgba(37, 37, 37, 0.26);
  padding: 10px;
  margin: 2px;
  border-radius: 10px;
  color: #FFF;
  font-weight: bold;
}
.line {
  margin: 3px;
  color: #FFF!important;

}
.crypto-name {
  font-size: 28px;
  background-color: transparent!important;
  color: gold;
  text-shadow: 0 0 6px rgba(0, 0, 0, 0.575);
}
.top .line .info {
  margin: 0;
}
.img_modale {
  filter: drop-shadow(0 0 9px rgba(255, 255, 255, 0.308));
}
</style>
