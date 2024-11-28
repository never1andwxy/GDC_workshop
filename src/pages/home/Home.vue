<script setup>
import TopNavbar from '../../components/TopNavbar.vue';
import NewArrivals from '../../components/new-arrivals/NewArrivals.vue';
</script>

<template src="./home.html"></template>
<style scoped src="./home.css"></style>

<script>
export default {
  mounted() {
    this.showMessage = this.$route.query.showMessage
  },
  methods: {
    messageClose() {
      this.showMessage = false
    }
  },
  components: {
    TopNavbar,
  },

  data() {
    return {
      showMessage: false
    };
  }
};
</script>