<template>
    <!-- Your HTML goes here -->
    <div class="home">
        <h1>Welcome</h1>
        <div>
            <table>
                <thead>
                <tr>
                    <th>Product</th>
                    <th>Amount</th>
                    <th>Action</th>
                </tr>
                </thead>
                <tr v-for="product in products" :key="product.id">
                    <td>{{product.name}}</td>
                    <td>{{product.amount}}</td>
                    <td><CustomButton v-bind:product="product.id" v-on:view-product="$emit('view-product',product.id)">
                        <span>
                            View {{product.name}}
                        </span>
                    </CustomButton></td>
                </tr>
            </table>
        </div>
    </div>
</template>

<script>
    import CustomButton from './CustomButton'

    export default {
        name: 'Index',
        active: true,
        props:["products"],
        components: {
            CustomButton
        },
        data() {
            return {
                amount: 1000,

                classObject: {
                    active: true,
                    'text-danger': false
                },
                myAlert: function () {
                    alert("Are you sure you want to submit the form")

                }
            }
        },

    }


</script>

<style>

    .active {
        color: blue;
    }

    label{
        padding:10px;
    }

    table, td, th {
        border: 1px solid #ddd;
        text-align: left;
    }

    table {
        border-collapse: collapse;
        width: 50%;
    }

    th, td {
        padding: 15px;
    }

</style>
