<template>
  <div class="hello">
    <h1 >{{product}}</h1>
    <img :src="image"/>
    <p v-bind:class="{colorRed:inStock}">{{show()}}</p>
    <p>{{showText}}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      image: 'https://cdn.vjshop.vn/hightech/may-choi-game/ps5/sony-ps-5-1.jpg',
      imageAlt: 'ps5 alt',
      product: 'ps5',
      productLink: 'https://bachtungps.com.vn/may-sony-playstation-5-ps5-1',
      quantity: 10,
      price: 10000,
      discount: 0.2,
      inStock: true,
      classObject: {
        'bg-green': true,
        'bg-blue': false
      }
    }
  },
  methods: {
    show() {
      return this.price -(this.price * this.discount)
    }
  },
  computed: {
    showText() {
      return 'PS5 ngon bo re'
    }
  },
  mounted() {

  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.colorRed {
  color: red;
}
h1, h2 {
  font-weight: normal;
}
.app 
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
img {
  height: 100px;
}
</style>
