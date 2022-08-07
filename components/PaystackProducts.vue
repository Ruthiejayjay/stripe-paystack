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
          PayStack Products
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
            v-for="(product, i) in products"
            :key="i"
          >
            <img
              class="object-cover w-32 h-32 rounded-full ring-4 ring-gray-300"
              :src="images[i]"
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

            <div class="flex mt-3 -mx-2">
              <p class="text xs">{{ product.price }}</p>
            </div>
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
      images: [],
    };
  },
  mounted() {
    var axios = require("axios");

    var config = {
      method: "get",
      url: "https://api.paystack.co/product",
      headers: {
        Authorization:
          "Bearer sk_test_179cd2bdf27a0372e0f2e355b682aaed2c0b7b97",
      },
    };

    axios(config)
      .then((response) => {
        this.products = response.data.data;

        //console.log("products", this.products);

        for (let i = 0; i < this.products.length; i++) {
          this.images.push(this.products[i].files[0].path);
          //console.log(this.images);
        }
        //console.log(this.products[0].files[0].path);
      })
      .catch(function (error) {
        console.log(error);
      });
  },
  methods: {},
};
</script>

<style>
</style>