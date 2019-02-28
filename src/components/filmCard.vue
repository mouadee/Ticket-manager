<template>
    <div class="card col-md-6">
        <img src="https://bit.ly/2EkJuoA" class="card-img-top" alt="film poster">
        <div class="card-body">
            <h5 class="card-title">Ticket Film 1</h5>
            <p class="card-text">Price: 23$</p>
            <a href="#" class="btn btn-success" @click="checkout()">Buy</a><br>
        </div>
    </div>
</template>

<script>
    export default {
        name: "filmCard",
        props: ["ticket"],
        methods: {
            checkout() {
                console.log(this.$emit('checkout').ticket);
            }
        },
    }
</script>
<style scoped>
    .card {
        width: 18rem;
        border: none;
    }
    img {
        width: 250px;
        margin: 0 auto;
    }
    .card-body {
        margin: 0 auto;
        text-align: center;
    }
</style>