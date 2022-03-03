<template>
  <div
    class="card card-compact rounded-none cursor-pointer"
    @mouseover="isHovering = true"
    @mouseout="isHovering = false"
  >
    <figure class="overflow-hidden">
      <img
        :class="isHovering ? 'scale-110' : ''"
        class="transition-transform duration-500"
        :src="imageSrc"
        alt="Shoes"
      />
    </figure>
    <div class="card-body">
      <p>
        <span class="relative">
          {{ name }}
          <span
            :class="isHovering ? 'w-full' : 'w-0'"
            class="absolute bottom-0 left-0 h-[1px] bg-base-content bg-red-500 duration-500"
          ></span>
        </span>
      </p>
      <h2 class="card-title">{{ price }}€</h2>
    </div>
  </div>
</template>

<script setup>
let isHovering = ref(false);

const props = defineProps({
  name: {
    type: String,
    required: true,
  },
  price: {
    type: Number,
    required: true,
  },
  imageSrc: {
    type: String,
    required: true,
  },
});
</script>
