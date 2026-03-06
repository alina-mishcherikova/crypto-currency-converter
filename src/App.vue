<template>
  <h1>Crypto</h1>
  <Input
    :changeAmount="changeAmount"
    :convert="convert"
    :favourite="favourite"
  />
  <p v-if="error != ''">{{ error }}</p>
  <p v-if="result != ''" className="result-text">{{ result }}</p>
  <Favourite :favs="favs" v-if="favs.length > 0" :getFromFavs="getFromFavs" />
  <div class="selectors">
    <Selector :setCrypto="setCryptoFirst" :cryptoNow="cryptoFirst" />
    <Selector :setCrypto="setCryptoSecond" :cryptoNow="cryptoSecond" />
  </div>
</template>
<script>
import Input from "./components/Input.vue";
import Selector from "./components/Selector.vue";
import Favourite from "./components/Favourite.vue";
import CryptoConvert from "crypto-convert";

const convert = new CryptoConvert();

export default {
  components: {
    Input,
    Selector,
    Favourite,
  },
  data() {
    return {
      amount: 0,
      cryptoFirst: "",
      cryptoSecond: "",
      error: "",
      result: 0,
      favs: [],
    };
  },
  methods: {
    favourite() {
      this.favs.push({
        from: this.cryptoFirst,
        to: this.cryptoSecond,
      });
    },
    getFromFavs(index) {
      this.cryptoFirst = this.favs[index].from;
      this.cryptoSecond = this.favs[index].to;
    },
    changeAmount(val) {
      this.amount = val;
    },
    setCryptoFirst(val) {
      this.cryptoFirst = val;
    },
    setCryptoSecond(val) {
      this.cryptoSecond = val;
    },
    async convert() {
      if (this.amount <= 0) {
        this.error = "You need to enter number bigger than 0";
        return;
      } else if (this.cryptoFirst == "" || this.cryptoSecond == "") {
        this.error = "Choose currency ";
        return;
      } else if (this.cryptoFirst == this.cryptoSecond) {
        this.error = "Choose other currency ";
        return;
      }

      this.error = "";

      await convert.ready();
      this.result = convert[this.cryptoFirst][this.cryptoSecond](this.amount);
    },
  },
};
</script>

<style scoped>
.selectors {
  display: flex;
  justify-content: space-around;
  width: 43.75rem;
  margin: 0 auto;
}
</style>
