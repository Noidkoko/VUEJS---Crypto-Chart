<template>
  <div class="hello">
    <h1>Bienvenue sur {{ msg }}</h1>
    <p>Ne pariez que ce vous pouvez perdre !</p>
    <h3>Liens Utiles</h3>
    <ul>
      <li>
        <a
          href="https://www.cashbackforex.com/tools/position-size-calculator"
          target="_blank"
          rel="noopener"
          >Calculateur de lots</a
        >
      </li>
      <li>
        <a href="https://coinmarketcap.com/fr/" target="_blank" rel="noopener"
          >CoinMarket Cap</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
