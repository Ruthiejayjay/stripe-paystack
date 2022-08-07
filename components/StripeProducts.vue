<template>
  <div>
    <section class="bg-white dark:bg-gray-900">
      <div class="container px-6 py-10 mx-auto">
        <h1
          class="
            text-3xl
            font-semibold
            text-center text-gray-800
            capitalize
            lg:text-4xl
            dark:text-white
          "
        >
          Stripe Products
        </h1>

        <p
          class="
            max-w-2xl
            mx-auto
            my-6
            text-center text-gray-500
            dark:text-gray-300
          "
        >
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Illo incidunt
          ex placeat modi magni quia error alias, adipisci rem similique, at
          omnis eligendi optio eos harum.
        </p>

        <div
          class="
            grid grid-cols-1
            gap-8
            mt-8
            xl:mt-16
            md:grid-cols-2
            xl:grid-cols-4
          "
        >
          <div
            class="
              flex flex-col
              items-center
              p-8
              transition-colors
              duration-200
              transform
              cursor-pointer
              group
              hover:bg-blue-600
              rounded-xl
            "
            v-for="product in products"
            :key="product.id"
          >
            <img
              class="object-cover w-32 h-32 rounded-full ring-4 ring-gray-300"
              :src="product.images"
              alt=""
            />

            <h1
              class="
                mt-4
                text-2xl
                font-semibold
                text-gray-700
                capitalize
                dark:text-white
                group-hover:text-white
              "
            >
              {{ product.name }}
            </h1>

            <p
              class="
                mt-2
                text-gray-500
                capitalize
                dark:text-gray-300
                group-hover:text-gray-300
              "
            >
              {{ product.description }}
            </p>

          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    var axios = require("axios");

    var config = {
      method: "get",
      url: "https://api.stripe.com/v1/products",
      headers: {
        Authorization:
          "Bearer  sk_test_51LIEnMDw37K7KqJsgA0MLKcjUNYnca6j2Fn4VseXUsSaQstpdWUloKZN75KT0Ia4aD48D1h9nMfxyUg36xtbQynz00LyjMYwbk",
      },
    };

    axios(config)
      .then( (response) => {
        this.products = response.data.data;
      })
      .catch(function (error) {
        console.log(error);
      });
  },
};
</script>

<style>
</style>