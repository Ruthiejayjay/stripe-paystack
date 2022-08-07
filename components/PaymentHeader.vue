<template>
  <div>
    <section class="relative pt-20 pb-32 2xl:py-40 bg-gray-800 overflow-hidden">
      <div
        class="absolute bottom-0 inset-x-0 h-full bg-gradient-zospace-1"
      ></div>
      <div
        class="
          absolute
          bottom-0
          inset-x-0
          h-3/5
          w-2full
          -ml-64
          -mb-12
          bg-gradient-zospace-2
          transform
          -rotate-6
        "
      ></div>
      <div class="relative container px-3 mx-auto">
        <div class="max-w-3xl mx-auto text-center">
          <span
            class="
              text-lg
              font-bold
              text-transparent
              bg-clip-text bg-gradient-to-br
              from-yellow-200
              to-orange-600
            "
            >Two ways to start!</span
          >
          <h2
            class="my-10 text-5xl lg:text-6xl font-bold font-heading text-white"
          >
            Payment Gateways
          </h2>
          <div class="max-w-md mx-auto">
            <p class="mb-20 text-lg text-gray-200">
             Test Two Payment Gateways for adding a product and view all products
            </p>
            <NuxtLink
              class="
                inline-block
                mb-4
                sm:mb-0 sm:mr-4
                py-4
                px-12
                text-white
                font-bold
                bg-blue-500
                hover:bg-blue-600
                rounded-full
                transition
                duration-200
              "
              to="/paystack"
              >Pay Stack</NuxtLink
            ><NuxtLink
              class="
                inline-block
                py-4
                px-12
                text-white
                font-bold
                border border-gray-50
                hover:border-gray-100
                rounded-full
              "
              to="/stripe"
              >Stripe</NuxtLink
            >
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>