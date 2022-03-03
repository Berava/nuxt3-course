<template>
  <div>
    <!-- <NuxtWelcome /> -->
    <h1 class="text-5xl text-center p-5">
      Category : {{ $route.params.categoryName }}
    </h1>
    <cards-container>
      <product-card
        v-for="product in products"
        :name="product.name"
        :price="product.price"
        :imageSrc="product.imageSrc"
      />
    </cards-container>
  </div>
</template>

<script setup>
const products = [
  {
    name: "Super Hoodie",
    price: 19,
    imageSrc: "https://api.lorem.space/image/shoes?w=400&h=225",
  },
  {
    name: "Super Tshirt",
    price: 14,
    imageSrc: "https://api.lorem.space/image/shoes?w=400&h=225",
  },
];
</script>
