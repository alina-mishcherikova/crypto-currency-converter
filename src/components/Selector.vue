<script>
export default {
  props: {
    setCrypto: {
      type: Function,
      required: true,
    },
    cryptoNow: {
      type: String,
      required: true,
    },
  },
  data() {
    return {};
  },
};
</script>

<template>
  <ul>
    <li
      @click="setCrypto('BTC')"
      :className="cryptoNow == 'BTC' ? 'active' : ''"
    >
      Bitcoin
    </li>
    <li
      @click="setCrypto('ETH')"
      :className="cryptoNow == 'ETH' ? 'active' : ''"
    >
      ETH
    </li>
    <li
      @click="setCrypto('USDT')"
      :className="cryptoNow == 'USDT' ? 'active' : ''"
    >
      USDT
    </li>
  </ul>
</template>

<style scoped>
ul {
  list-style: none;
  width: 12.5rem;
  padding: 0;
  border-radius: 3px;
  border: 3px solid #000;
}
li {
  display: block;
  background: #1a032d;
  color: #fff;
  padding: 1.25rem 0;
}
li:hover,
li.active {
  background: #24043e;
  cursor: pointer;
}
</style>
