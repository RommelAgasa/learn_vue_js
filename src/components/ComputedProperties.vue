<template>


    <h2>Full Name: {{ fullName }} </h2>
    <h2>Total Price: {{ totalPrice }}</h2>


    <button
        @click="items.push({id: 4, name: 'Tablet', price: 200})">
        Add Item
    </button>

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
            ]
        }
    },
    methods:{

    },
    computed: {
        fullName(){
            return `${this.firstName} ${this.lastName}`;
        },
        totalPrice(){
            return this.items.reduce((total, curr) => (total += curr.price), 0);
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