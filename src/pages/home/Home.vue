<script setup>
import TopNavbar from '../../components/TopNavbar.vue';
import NewArrivals from '../../components/new-arrivals/NewArrivals.vue';

</script>

<template src="./home.html"></template>
<style scoped src="./home.css"></style>

<script>
export default {
  methods: {
    messageClose(){
      showMessage: false
    }
  },
  components: {
    TopNavbar,
  },

  data() {
    return {
      showMessage: true
    };
  }
};
</script>