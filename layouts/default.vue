<template>
  <div>
    <PaymentNav />
    <Nuxt />
    <PaymentFooter />
  </div>
</template>

<script>
import PaymentNav from "~/components/PaymentNav.vue";
import PaymentFooter from "~/components/PaymentFooter.vue";
export default {
  components: {
    PaymentNav,
    PaymentFooter,
  },
};
</script>

<style>
</style>