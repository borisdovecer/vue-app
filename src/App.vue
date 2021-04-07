<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <ItemList :items="items" msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue'

export default {
  name: 'App',
  components: {
    ItemList
  },

  data() {
    let items = ["item 1", "item 2", "item 3", "item 4", "item 5", "item 6", "item 7", "item 8", "item 9", "item 10",
      "item 11", "item 12", "item 13", "item 14", "item 15", "item 16", "item 17", "item 18", "item 19", "item 20",
      "item 21", "item 22", "item 23", "item 24", "item 25", "item 26", "item 27", "item 28", "item 29", "item 30",
      "item 31", "item 32", "item 33", "item 34", "item 35", "item 36", "item 37", "item 38", "item 39", "item 40",
      "item 41", "item 42", "item 43", "item 44", "item 45", "item 46", "item 47", "item 48", "item 49", "item 50",
      "item 51", "item 52", "item 53", "item 54", "item 55", "item 56", "item 57", "item 58", "item 59", "item 60",
      "item 61", "item 62", "item 63", "item 64", "item 65", "item 66", "item 67", "item 68", "item 69", "item 70",
      "item 71", "item 72", "item 73", "item 74", "item 75", "item 76", "item 77", "item 78", "item 79", "item 80"
    ];
    return {
      items: [],
      itemsfull: items
    };
  },
  methods: {
    getInitialItems() {
      this.items = this.itemsfull.slice(0, 20)
    },
    getNextItem() {
      let chunk = 20
      window.onscroll = () => {
        let bottomOfWindow = document.documentElement.scrollTop + window.innerHeight === document.documentElement.offsetHeight;
        if (bottomOfWindow) {
          if(this.items.length<this.itemsfull.length){
            let arr = this.itemsfull.slice(chunk,chunk+20)
            arr.forEach(i => {
              this.items.push(i)
            })
            chunk+=20
          }
        }
      }
    },
  },
  beforeMount() {
    this.getInitialItems();
  },
  mounted() {
    this.getNextItem();
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
