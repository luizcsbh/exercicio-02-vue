<template>
  <div>
    <table class="table">
      <thead class="thead-dark">
        <tr>
          <th scope="col">Product</th>
          <th scope="col">Price</th>
          <th scope="col">Quantity</th>
          <th scope="col">Category</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>{{product.name}}</td>
          <td class="money">{{this.formatMoney(product.price)}} </td>
          <td>{{product.quantity}} </td>
          <td>{{product.category}} </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    product: Object
  },
  methods:{
    formatMoney(money){
      return new Intl.NumberFormat('en-US',{style: 'currency', currency:'USD'}).format(money)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
