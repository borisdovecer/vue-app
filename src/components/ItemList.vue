<template>
  <div>
    <h1>Item List</h1>
    <button v-on:click="isHidden = true">Show items</button>
    <ul
        v-for="item in items"
        :key="item.first"
    >
      <li  v-if="isHidden">{{item}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ItemList',
  props: {
    msg: String,
    items: Array
  },
  data(){
    return {
      isHidden: false
    }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
</style>