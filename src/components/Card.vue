<template>
  <div @mouseover="hover = true" @mouseleave="hover = false" class="relative">
    <img class="rounded-lg" :src="src" />
    <div
      v-if="hover"
      class="absolute bg-dark opacity-50 inset-0 w-full h-full rounded-lg"
    ></div>
    <div
      v-if="hover"
      class="absolute top-0 w-full h-full flex flex-col justify-between p-3"
    >
      <div class="flex items-center justify-between">
        <button class="flex items-center" type="button" name="button">
          <p class="font-semibold text-white">{{ board }}</p>
          <span class="material-icons text-white">expand_more</span>
        </button>

        <button
          class="rounded-full py-3 px-5 text-white bg-primary font-semibold"
          type="button"
          name="button"
        >
          Save
        </button>
      </div>
      <div class="flex items-center w-full">
        <button
          class="
            ml-auto
            mr-2
            bg-white
            rounded-full
            w-8
            h-8
            flex
            item-center
            justify-center
            text-dark
            opacity-75
            hover:opacity-100
          "
          type="button"
          name="button"
        >
          <span class="material-icons text-base">ios_share</span>
        </button>
        <button
          class="
            bg-white
            rounded-full
            w-8
            h-8
            flex
            item-center
            justify-center
            text-dark
            opacity-75
            hover:opacity-100
          "
          type="button"
          name="button"
        >
          <span class="material-icons text-base">more_horiz</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["src", "board"],
  data() {
    return {
      hover: false,
    };
  },
};
</script>

<style scoped></style>
