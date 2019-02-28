<template>
  <div id="app">
    <p class="text-center mb-4 mt-4 lead">Ticket Management Example :</p>
    <div class="container">
      <div class="row">
        <filmCard :ticket="ticket" v-on:checkout="checkout"></filmCard>
        <cart :ticket="ticket" v-on:removing="removing" v-on:checkout="checkout"></cart>
      </div>
    </div>
  </div>
</template>

<script>
  import filmCard from './components/filmCard'
  import cart from './components/cart'
export default {
  components: {
    filmCard,
    cart
  },
  data() {
    return {
      ticket: 0
    }
  },
  methods: {
    checkout() {
      return this.ticket ++
    },
    removing() {
      if (this.ticket <= 0) {
        alert('Ticket can\'t be null!')
      } else {
        this.ticket --;
      }
    }
  },
}
</script>
