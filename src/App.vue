<template>
  <img
    width="120"
    alt="Vue logo"
    src="https://cdn-icons.flaticon.com/png/512/6101/premium/6101402.png?token=exp=1658214181~hmac=78cb6df8bc7d9a236756f1b9dd8b7189"
  />
  <Header msg="crypto-charts.io" />

  <mainContainer :info="info" />
</template>

<script>
import Header from "./components/Header.vue";
import mainContainer from "./components/mainContainer.vue";
import axios from "axios"



export default {
  name: "App",
  components: {
    Header,
    mainContainer,
  },
  data() {
    return {
      info: null,
    };
  },
  beforeMount() {
    axios
      .get("https://api.coingecko.com/api/v3/coins/markets?vs_currency=eur")
      .then((response) => (this.info = response.data));
  },
};
</script>

<style>
body {
  background-color: #2c3e50;
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
  text-align: center;
}
</style>
