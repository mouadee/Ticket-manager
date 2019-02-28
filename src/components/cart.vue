<template>
    <div class="card col-lg">
        <div class="card-header">Cart</div>
        <div class="card-body">
            <div class="products">
                <b>Ticket Title: {{ticket_title}}</b> <br><br>
                <label for="myNumber"><b>Number of ticket:</b></label>
                <input id="myNumber" type="number" min="0" :value="ticket">
                <button class="btn btn-danger" @click="removing()">-</button>&nbsp;
                <button class="btn btn-success" @click="checkout()">+</button>
                <br><br><br>
                <b>Total Price: {{ticket_price}}$</b> <br><br>
                <button class="btn btn-warning" @click="alerting()">Check out</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "card",
        methods: {
            alerting() {
                if (document.getElementById("myNumber").value <= 0) {
                    alert('Please pick a ticket!')
                } else {
                    /*const x = document.getElementById('afterCheckout');
                    const y  =document.createTextNode('All is good ...');
                    x.appendChild(y);*/
                    window.location.href = "https://www.example.com";
                }
            },
            removing() {
                this.$emit('removing')
            },
            checkout() {
                this.$emit('checkout')
            }
        },
        props: {
            ticket: {
                type: Number,
                default: 0
            },
        },
        data() {
            return {
                ticket_title: 'Ticket Film 1',
                ticket_price: 23,
            }
        },
    }
</script>

<style scoped>
    b, label {
        color: rgba(13, 83, 177, 0.98);
    }
    .card {
        height: 330px;
        border: none;
    }
    input {
        width: 40px;
        text-align: center;
        background: transparent;
        border: none;
        color: #FFF;
        outline: none
    }
    .btn {
        outline: none;
    }
</style>