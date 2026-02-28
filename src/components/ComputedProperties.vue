<template>


    <h2>Full Name: {{ fullName }} </h2>
    <button @click="changeFullName">Change fullname</button>


    <h2>Total Price: {{ totalPrice }}</h2>

    <button
        @click="items.push({id: 4, name: 'Tablet', price: 200})">
        Add Item
    </button>

    <h2>Method Total: {{ getTotal() }}</h2>

    <input type="text" v-model="country">

    <div v-for="item in items" :key="item.id">
        <h2 v-if="item.price > 100">{{ item.name }} - {{ item.price }}</h2>
    </div>

    <!-- computed properties v-for -->
     <h2 v-for="item in expensiveItems" :key="item.id">{{ item.name }} - {{ item.price }}</h2>

</template>


<script>


export default {
    name: 'ComputedProperties',
    data(){
        return {
            firstName: 'Rommel',
            lastName: 'Agasa',
            items: [
                {id: 1, name: 'TV', price: 100},
                {id: 2, name: 'Laptop', price: 500},
                {id: 3, name: 'Phone', price: 300}
            ],
            country: '',
        }
    },
    methods:{
        changeFullName(){
            this.fullName = 'Jhon Doe';
        },
        getTotal() { // this will be called every time the component re-renders, even if the items array has not changed. This is because methods are not cached and will be executed every time they are called in the template.
            console.log('get Total Method');
            return this.items.reduce((total, curr) => (total += curr.price), 0);
        }
    },
    computed: {

        fullName: {
            get() {
                return `${this.firstName} ${this.lastName}`;
            },
            set(value) {
                const names = value.split(' ');
                this.firstName = names[0];
                this.lastName = names[names.length - 1];
            }
        },
        // {
        //     return `${this.firstName} ${this.lastName}`;
        // },
        totalPrice(){
            console.log('Total computed property');
            return this.items.reduce((total, curr) => (total += curr.price), 0);
        },
        expensiveItems(){
            return this.items.filter(item => item.price > 100);
        }
    }
}

</script>

<style>
#computed-properties {
    font-family: Arial, sans-serif;
    padding: 20px;
}

</style>