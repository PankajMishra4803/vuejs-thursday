<template>
    <div><p>ProductList</p>
    <table>
        <tr>
            <th>Product Name</th>
            <th>Quantity</th>
        </tr>
        <tr v-for="(product, ind) in products" :key="ind">
            <td>{{product.productName}}</td>
            <td>{{product.quantity}}</td>
           
        </tr>
    </table>
     <form v-on:submit="submitForm" action="#" method="post">
        <p>
          <label for="productName">ProductName: </label>
          <input type="text" id="productName" v-model="productName"  name="productName"/>
        </p>
        <p>
          <label for="quantity">Quantity: </label>
          <input type="text" id="quantity" v-model="quantity"  name="quantity"/>
        </p>
        <button type="submit" class="button is-danger">Submit</button>
    </form>
    </div>
</template>
<script>
export default {
    name:'ProductList',
    data(){
        return{
            productName:'',
            quantity:'',
         products:[
            {productName:'Redmi23', quantity:1},
            {productName:'Samsung', quantity:1},
            {productName:'Apple', quantity:1},
            {productName:'Redmi', quantity:1}
         ]
        }
    },
    methods:{
        submitForm:function(e){
           e.preventDefault();
           let productObj = {};
           productObj['productName'] = this.productName;
           productObj['quantity'] = this.quantity
           this.products.push(productObj);
        }
    }
}
</script>
<style scoped>
table, th, td {
  border: 1px solid black;
}
</style>