<template>
  <!-- Section 1 -->
  <section
    class="relative flex items-center justify-center w-full h-full bg-white"
  >
    <div class="relative hidden w-1/4 h-full bg-center bg-cover lg:block"></div>
    <div
      class="
        absolute
        top-0
        left-0
        hidden
        w-1/4
        h-full
        bg-center bg-cover
        lg:block
      "
      style="
        background-image: url('https://cdn.devdojo.com/images/november2021/scenic.jpeg');
      "
    >
      <div
        class="
          absolute
          inset-0
          w-full
          h-full
          bg-gradient-to-b
          from-transparent
          to-gray-900
        "
      ></div>
      <NuxtLink
        to="/"
        class="
          absolute
          bottom-0
          left-0
          flex
          items-center
          w-auto
          m-5
          font-medium
          text-white
          group
        "
      >
        <svg
          class="w-5 h-5"
          fill="currentColor"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z"
            clip-rule="evenodd"
          ></path>
        </svg>
        Return Home
        <span
          class="
            absolute
            overflow-hidden
            left-0
            block
            pl-5
            h-0.5
            w-full
            bottom-0
            -mb-0.5
          "
        >
          <span
            class="
              absolute
              rounded-full
              bg-white
              duration-200
              ease-in-out
              transition-all
              h-0.5
              w-0
              group-hover:w-full
            "
          ></span>
        </span>
      </NuxtLink>
    </div>

    <div
      class="
        flex
        items-center
        justify-center
        w-full
        h-full
        px-8
        py-32
        lg:w-3/4
        sm:px-0
      "
    >
      <div class="w-full max-w-sm mx-auto">
        <div class="relative flex items-center mb-8">
          <a
            href="#_"
            class="
              inline-block
              px-3
              p-1.5
              font-sans
              text-left text-white
              bg-gray-800
              rounded
              no-underline
              cursor-pointer
              focus:no-underline
            "
          >
            <span class="text-lg font-bold leading-tight">NewDevz</span>
          </a>
        </div>
        <h1
          class="
            text-gray-600
            font-medium
            text-2xl
            border-b border-gray-300
            pb-2.5
            mb-2.5
          "
        >
          Create A Product on Stripe
        </h1>

        <div class="relative flex flex-col-reverse mb-5">
          <input
            type="text"
            v-model="name"
            name="name"
            class="
              border-gray-300
              focus:border-blue-600
              peer
              border
              rounded-md
              px-3.5
              py-3
              focus:outline-none
              focus:ring-2
              focus:ring-offset-1
              focus:ring-blue-600
              focus:ring-opacity-0
              caret-blue-600
            "
            placeholder="Enter Product Name"
          />
          <label
            for="name"
            class="mb-2 font-medium text-gray-500 peer-focus:text-blue-600"
            >Name</label
          >
        </div>

        <div class="relative flex flex-col-reverse mb-5">
          <input
            type="text"
            v-model="description"
            name="description"
            class="
              border-gray-300
              focus:border-blue-600
              peer
              border
              rounded-md
              px-3.5
              py-3
              focus:outline-none
              focus:ring-2
              focus:ring-offset-1
              focus:ring-blue-600
              focus:ring-opacity-0
              caret-blue-600
            "
            placeholder="Enter Product Description"
          />
          <label
            for="description"
            class="mb-2 font-medium text-gray-500 peer-focus:text-blue-600"
            >Description</label
          >
        </div>

        <div class="relative flex flex-col-reverse mb-5">
          <input
            type="text"
            v-model="price"
            name="price"
            class="
              border-gray-300
              focus:border-blue-600
              peer
              border
              rounded-md
              px-3.5
              py-3
              focus:outline-none
              focus:ring-2
              focus:ring-offset-1
              focus:ring-blue-600
              focus:ring-opacity-0
              caret-blue-600
            "
            placeholder="Enter Product Price"
          />
          <label
            for="price"
            class="mb-2 font-medium text-gray-500 peer-focus:text-blue-600"
            >Price</label
          >
        </div>

        <div class="relative flex flex-col-reverse mb-5">
          <input
            type="text"
            v-model="currency"
            name="currency"
            class="
              peer
              border-gray-300
              focus:border-blue-600
              border
              rounded-md
              px-3.5
              py-3
              focus:outline-none
              focus:ring-2
              focus:ring-offset-1
              focus:ring-blue-600
              focus:ring-opacity-0
              caret-blue-600
            "
            placeholder="NGN"
          />
          <label
            for="currency"
            class="mb-2 font-medium text-gray-500 peer-focus:text-blue-600"
            >Currency</label
          >
        </div>

        <div class="relative flex flex-col-reverse mb-5">
          <input
            type="text"
            v-model="image"
            name="img"
            class="
              peer
              border-gray-300
              focus:border-blue-600
              border
              rounded-md
              px-3.5
              py-3
              focus:outline-none
              focus:ring-2
              focus:ring-offset-1
              focus:ring-blue-600
              focus:ring-opacity-0
              caret-blue-600
            "
            placeholder="Image Url"
          />
          <label
            for="img"
            class="mb-2 font-medium text-gray-500 peer-focus:text-blue-600"
            >Product Image</label
          >
        </div>

        <div class="relative flex flex-col">
          <button
            @click="createProduct"
            class="
              w-full
              rounded
              bg-blue-600
              hover:opacity-90
              text-white
              py-3.5
              px-2
              text-center
              font-medium
            "
          >
            Create
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      description: "",
      price: "",
      currency: "",
      image: "",
    };
  },
  methods: {
    createProduct() {
      var axios = require("axios");
      var qs = require("qs");
      var data = qs.stringify({
        name: this.name,
        description: this.description,
        "default_price_data[currency]": this.currency,
        "default_price_data[unit_amount]": this.price,
        "images[0]": this.image,
      });
      console.log("name", this.name);
      console.log("description", this.description);
      console.log("price", this.price);
      console.log("currency", this.currency);
      console.log("image", this.image);

      var config = {
        method: "post",
        url: "https://api.stripe.com/v1/products",
        headers: {
          Authorization:
            "Bearer  sk_test_51LIEnMDw37K7KqJsgA0MLKcjUNYnca6j2Fn4VseXUsSaQstpdWUloKZN75KT0Ia4aD48D1h9nMfxyUg36xtbQynz00LyjMYwbk",
          "Content-Type": "application/x-www-form-urlencoded",
        },
        data: data,
      };

      axios(config)
        .then(function (response) {
           Swal.fire({
              position: "top-end",
              icon: "success",
              title: "Product Uploaded Successfully",
              showConfirmButton: false,
              timer: 3000,
            });
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
};
</script>

<style>
</style>