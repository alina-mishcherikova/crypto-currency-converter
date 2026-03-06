<script>
export default {
  props: {
    favs: {
      type: Array,
      required: true,
    },
    getFromFavs: {
      type: Function,
      required: true,
    },
  },
};
</script>

<template>
  <h2>Variants in a favourite</h2>
  <div @click="getFromFavs(index)" v-for="(el, index) in favs" :key="index">
    <span>{{ el.from }}</span>
    <span>{{ el.to }}</span>
  </div>
</template>

<style scoped>
h2 {
  color: white;
}

div {
  display: flex;
  justify-content: space-between;
  width: 20rem;
  margin: 0.75rem auto;
  transition: all 500ms ease;
}
span {
  padding: 0.75rem 1rem;
  background: #8c00ff;
  color: white;
}
div:hover {
  opacity: 0.7;
  transform: scale(1.1);
  cursor: pointer;
}
</style>
