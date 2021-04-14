<template>
  <div>
        <h2>------------ Computed Properties ---------</h2>
        <h2>Full Name: {{firstName}} {{lastName}}</h2>
        <h2>Computed Full Name: {{fullName}}</h2>
        <button @click="changeFullName">Change Full Name</button>

        <button @click="products.push({id: 4, title: 'Keyboard', price: 50,})">Add item</button>
        <h2>
            Total - {{ products.reduce((total, curr) => (total = total + curr.price), 0) }}
        </h2>
        <h2>Method Total - {{totalPrice()}}</h2>
        <h2>Computed Total - {{getPrice}}</h2>
        <input type="text" v-model="country">

        <div v-for="product in products" :key="product.id">
            <h2 v-if="product.price > 100">{{product.title}} - {{product.price}}</h2>
        </div>

        <h2 v-for="item in expensiveItems" :key="item.id">
            {{item.title}} - {{item.price}}
        </h2>
  </div>
</template>

<script>
export default {
    name: "ComputedProperties",
    data(){
        return{
            firstName: 'Bruce',
            lastName: 'Wayne',
            products: [
                {
                    id: 1,
                    title: 'TV',
                    price: 100,
                },
                {
                    id: 2,
                    title: 'Phone',
                    price: 200,
                },
                {
                    id: 3,
                    title: 'Laptop',
                    price: 300
                }
            ],
            country: '',
        }
    },
    computed: {
        /*fullName(){
            return `${this.firstName} ${this.lastName}`
        },*/
        fullName:{
            get(){
                return `${this.firstName} ${this.lastName}`
            },
            set(value){
                const names = value.split('')
                this.firstName = names[0]
                this.lastName = names[1]
            }
        },
        getPrice(){
            console.log('From Computed Property');            
            return this.products.reduce((total, curr) => (total = total + curr.price), 0)
        },
        expensiveItems(){
            return this.products.filter(item => item.price > 100)
        }
    } ,   
    methods: {
        totalPrice(){
            console.log('From Method Property');
            return this.products.reduce((total, curr) => (total = total + curr.price), 0)
        },
        changeFullName(){
            this.fullName = 'Clark Kent'
        }     
    },

}
</script>

<style>

</style>