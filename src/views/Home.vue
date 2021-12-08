<template>
  <div class="home">
      <!-- <header class="top-bar spread">
        <nav class="top-bar-nav">
          <a href="#" class="top-bar-link">
            <i class="icofont-spoon-and-fork"></i>
            <span>Home</span>
          </a>
          <a href="views/products.html" class="top-bar-link">
            <span>Products</span>
          </a>
          <a href="views/past-orders.html" class="top-bar-link">
            <span>Past Orders</span>
          </a>
        </nav>
        <a href="#" class="top-bar-cart-link">
          <i class="icofont-cart-alt icofont-1x"></i>
          <span @click="toggleSidebar">Cart({{totalQuantity}})</span>
        </a>
      </header> -->

      <div class="splash-container">
        <div class="splash">
          <h1>Splendid Food</h1>
        </div>
      </div>

      <main class="wrapper">

        <h2>Recommended</h2>

        <div class="recommended">

          <div class="card" v-for="(item, i ) in this.inventory.slice(0,3)" :key="item.id">
            <div class="card-title">
              {{item.name}}
            </div>
            <div class="card-body">
              <i class="icofont-10x icofont-{{item.icon}}"></i>
              <form>
                <div class="row">
                  <div class="cell">
                    <label>Type:</label>
                  </div>
                  <div class="cell">
                    <em>{{item.type}}</em>
                  </div>
                </div>
                <div class="row">
                  <div class="cell">
                    <label>Price:</label>
                  </div>
                  <div class="cell">
                    {{item.price.USD}}
                  </div>
                </div>
                <div class="row">
                  <div class="cell">
                    <label>Quantity:</label>
                  </div>
                  <div class="cell">
                    <input type="number" v-model="item.quantity">
                  </div>
                </div>
              </form>
            </div>
            <div class="card-footer">
              <button @click="addToCart(item.name, i)" class="btn btn-light">
                Add to cart
              </button>
            </div>
          </div>
        </div>

      </main>
  </div>
</template>

<script>
// // @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import food from '../food.json'

export default {
  name: 'Home',
  data () {
    return {
      inventory: food
    }
  },
  components: {}
}
</script>
