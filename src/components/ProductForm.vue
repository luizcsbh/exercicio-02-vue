<template>
    <div class="conteiner">
        <div>
            <h1>Insert new product</h1>
        </div>
        <div class="form-group">
            <form @submit="onFormSubmit">
                <div class="form-group">
                    <label for="InputName">Name</label>
                    <input type="text" class="form-control" id="InputName" placeholder="Name of product" v-model="name">
                    <p class="warning">{{nameError}}</p>
                </div>
                <div class="form-group">
                    <label for="InputPrice">Price</label>
                    <input type="number" class="form-control" id="InputPrice" placeholder="$ 0.00" step="0.01" v-model="price">
                    <p class="warning">{{priceError}}</p>
                </div>
                <div class="form-group">
                    <label for="InputQuantity">Quantity</label>
                    <input type="number" class="form-control" id="InputQuantity" placeholder="Enter quantity" step="1" v-model="quantity">
                    <p class="warning">{{quantityError}}</p>
                </div>
                <div>
                    <label for="InputCategory">Category</label>
                    <input type="text" class="form-control" id="InputCategory" placeholder="Enter a category"  v-model="category">
                    <p class="warning">{{categoryError}}</p>
                </div>
                <button class="btn btn-primary" type="submit">Submit</button>
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        name:'ProductForm',
        data(){
            return{
                name: "",
                price: "",
                quantity: "",
                category: "",
                isNameLimitExceeded: false,
                isPriceNotNegative: false,
                isQuantityNotNegative: false,
                isCategoryLimitExceeded: false,
                nameError: "",
                priceError: "",
                quantityError: "",
                categoryError: ""
            }
        },
        props: {
            insertProduct: Function
        },
        methods: {
            onFormSubmit(e){
                e.preventDefault();
                this.insertProduct({
                    name: this.name,
                    price: this.price,
                    quantity: this.quantity,
                    category: this.category
                });
            }
        },
        watch: {
            name(){
                if (this.name.length > 15){
                    this.isNameLimitExceeded = true
                    this.nameError = "The product name cannot exceed 15 characters!"
                } else {
                    this.isNameLimitExceeded =false
                    this.nameError = ""
                }
            },
            price(){
                if (this.price < 0){
                    this.isPriceNotNegative = true
                    this.priceError = "The price cannot be less than zero!"
                } else {
                    this.isPriceNotNegative =false
                    this.priceError = ""
                }
            },
            quantity(){
                if (this.quantity < 0){
                    this.isQuantityNotNegative = true
                    this.quantityError = "The quantity cannot be less than zero!"
                } else {
                    this.isQuantityNotNegative =false
                    this.quantityError = ""
                }
            },
            category(){
                if (this.category.length > 15){
                    this.isCategoryLimitExceeded = true
                    this.categoryError = "The product category cannot contain more than 15 characters!"
                } else {
                    this.isCategoryLimitExceeded =false
                    this.categoryError = ""
                }
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.warning{
    color: red;
    font-weight: bold;
    font-size: 15px;
}
.conteiner{
    display: flex;
    flex-direction: column;
    align-items: center;    
}
</style>
