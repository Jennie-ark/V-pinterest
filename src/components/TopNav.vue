<template>
  <div class="px-3 py-4 flex items-center justify-between">
    <div class="flex items-center">
      <!--Logo-->
      <button
        class="rounded-full hover:bg-light p-3 flex items-center justify-center"
        type="button"
        name="button"
      >
        <img class="h-6 w-6" src="logo.png" alt="logo" />
      </button>
      <!--Buttons home and today-->
      <button
        :class="`${
          selectedTab === item.key
            ? 'bg-dark text-white'
            : 'text-dark hover:bg-light'
        }
                     rounded-full py-3 px-4 font-semibold`"
        v-for="(item, i) in tabItems"
        :key="i"
        @click="selectedTab = item.key"
        type="button"
        name="button"
      >
        {{ item.name }}
      </button>
    </div>
    <!--Search panel-->
    <div class="flex-grow relative">
      <span class="material-icons absolute mt-3 ml-3 text-muted">search</span>
      <input
        class="
          outline-none
          text-muted
          w-full
          hover:bg-light
          rounded-full
          bg-lightGray
          py-3
          pr-3
          pl-10
        "
        placeholder="Search"
        type="text"
      />
    </div>
    <!--notifications-->
    <div class="flex items-center">
      <button
        class="
          relative
          rounded-full
          hover:bg-light
          flex
          items-center
          justify-center
          p-3
        "
        type="button"
        name="button"
      >
        <span class="material-icons text-2xl text-muted">notifications</span>
        <div
          class="
            rounded-full
            h-5
            w-5
            bg-primary
            text-white
            flex
            items-center
            justify-center
            absolute
            mb-5
            ml-5
          "
        >
          4
        </div>
      </button>
      <!-- Text sms-->
      <button
        class="
          relative
          rounded-full
          hover:bg-light
          flex
          items-center
          justify-center
          p-3
        "
        type="button"
        name="button"
      >
        <span class="material-icons text-2xl text-muted">textsms</span>
        <div
          class="
            rounded-full
            h-5
            w-5
            bg-primary
            text-white
            flex
            items-center
            justify-center
            absolute
            mb-5
            ml-5
          "
        >
          1
        </div>
      </button>
      <!-- Profile-->
      <button
        class="rounded-full hover:bg-light p-3 flex items-center justify-center"
        type="button"
        name="button"
      >
        <img class="rounded-full h-6 w-6" src="profile.jpg" alt="logo" />
      </button>
      <button
        class="
          w-6
          h-6
          hover:bg-light
          rounded-full
          flex
          items-center
          justify-center
        "
        type="button"
        name="button"
      >
        <span class="material-icons text-muted">expand_more</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TopNav",
  data() {
    return {
      tabItems: [
        { name: "Home", key: "home" },
        { name: "Today", key: "today" },
      ],
      selectedTab: "home",
    };
  },
};
</script>

<style scoped></style>
