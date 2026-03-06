<script>
export default {
  props: {
    changeAmount: {
      type: Function,
      required: true,
    },
    convert: {
      type: Function,
      required: true,
    },
    favourite: {
      type: Function,
      required: true,
    },
  },
};
</script>

<template>
  <input
    min="0"
    type="number"
    @input="changeAmount($event.target.value)"
    placeholder="Enter a number"
  />
  <br />
  <button @click="convert()">Convert</button>
  <button @click="favourite()">Add to favorite</button>
</template>

<style scoped>
input {
  border-radius: 4px;
  border: 0px;
  padding: 0.8rem 1rem;
  outline: none;
  background: #fafafa;
  color: #333;
  width: 30rem;
  font-size: 1.2rem;
}
button {
  margin: 2rem;
  padding: 1rem 1.25rem;
  color: white;
  text-transform: uppercase;
  cursor: pointer;
  background: #1a032d;
  border: 0;
  border-radius: 3px;
}
</style>
