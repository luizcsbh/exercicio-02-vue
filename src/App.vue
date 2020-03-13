<template>
  <div id="app">
    <ProductList
      :productList="productList"
    />
    <ProductForm
      :insertProduct="insertProduct"
    />
  </div>
</template>

<script>
import ProductList from './components/ProductList'
import ProductForm from './components/ProductForm'

export default {
  name: 'App',
  data() {
      return{
          productList: [
              {
                code: 1,
                name: "MacBook Air",
                price: 1099.00,
                quantity: 5,
                category: "notebook"
              },
              {
                code: 2,
                name: "MacBook Pro",
                price: 1299.00,
                quantity: 20,
                category: "notebook"
              },
              {
                code: 3,
                name: "iMac",
                price: 1099.00,
                quantity: 15,
                category: "desktop"
              },
              {
                code: 4,
                name: "iMac Pro",
                price: 4999.00,
                quantity: 10,
                category: "desktop"
              },
              {
                code: 5,
                name: "Mac Pro",
                price: 5999.00,
                quantity: 30,
                category: "server"
              },
              {
                code: 6,
                name: "iPad Pro",
                price: 799.00,
                quantity: 250,
                category: "tablet"
              },
              {
                code: 7,
                name: "iPad Air",
                price: 499.00,
                quantity: 300,
                category: "tablet"
              },
              {
                code: 8,
                name: "iPad",
                price: 499.00,
                quantity: 400,
                category: "tablet"
              },
              {
                code: 9,
                name: "iPad mini",
                price: 399.00,
                quantity: 150,
                category: "tablet"
              },
              {
                code: 10,
                name: "iPhone 11 Pro",
                price: 999.00,
                quantity: 675,
                category: "smartphone"
              },
              {
                code: 11,
                name: "iPhone 11",
                price: 699.00,
                quantity: 700,
                category: "smartphone"
              },
              {
                code: 12,
                name: "iPhone Xr",
                price: 599,
                quantity: 200,
                category: "smartphone"
              },
              {
                code: 8,
                name: "iPhone 8",
                price: 449.00,
                quantity: 100,
                category: "smartphone"
              },
              {
                code: 14,
                name: "Apple Watch",
                price: 399.00,
                quantity: 125,
                category: "smartwatch"
              },
              {
                code: 15,
                name: "Apple TV 4K",
                price: 199.00,
                quantity: 450,
                category: "set box"
              }
          ]
      }
  },
  components: {
    ProductList,
    ProductForm
  },
  methods: {
    insertProduct(product){
      this.productList = this.productList.concat({
        name: product.name,
        price: product.price,
        quantity: product.quantity,
        category: product.category
      })
    }
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