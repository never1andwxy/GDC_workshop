<script setup>
import TopNavbar from '../../components/TopNavbar.vue';
import { useCart } from '/src/store/cart.js'
const store = useCart()
</script>

<template src="./cart.html"></template>
<style scoped src="./cart.css"></style>

<script>
import { mapState, mapActions } from 'pinia'
import JapanPostalCode from 'japan-postal-code';

export default {
  components: {
    TopNavbar
  },

  mounted() {
    //console.log('mounted', this.contents)
  },

  computed: {
    ...mapState(useCart, {
      contents: 'getContents',
      count: 'count',
      cartTotal: 'total'
    }),

    total() {
      return Math.max(this.cartTotal - this.promo.value, 0).toFixed(2);
    }
  },

  methods: {
    ...mapActions(useCart, [
      'clearCart'
    ]),

    getPostcode() {
      JapanPostalCode.get(this.zipCode, function (address) {
        console.log(address)
      })
      return {
        prefecture: "tokyo",
        address: "kawasakishi~~~~"
      }
    }
  },

  data() {
    return {
      currency: {
        name: 'JPY',
        symbol: '￥'
      },

      promo: {
        code: 'EXAMPLECODE',
        value: 5
      },

      zipCode: ""
    };
  },
};
</script>