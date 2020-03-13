<template>
    <div>
        <div>
            <h1>Product List Here!</h1>
        </div>
        <div>
            <ul>
                <li v-for="product in productList" v-bind:key="product.code">  
                    <ProductItem :product="product" />
                </li>
            </ul>
        </div>
        <div>
            <h5>The quantity of products in the List: <span>{{totalProducts}}</span></h5>
        </div>
        
    </div>
</template>

<script>
    import ProductItem from './ProductItem'
    export default {
        name: 'ProductList',
        props: {
            productList: Array
        },
        components: {
            ProductItem
        },
        computed: {
            totalProducts(){
                return this.productList.length;
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  ul {
    list-style-type: none;
    margin: 10px;
    padding: 0px;
  }

  li{
    margin-bottom: 10px;
  }
</style>
