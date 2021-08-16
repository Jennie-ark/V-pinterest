<template>
  <div id="app">
    <TopNav />
    <Loader v-if="loading" />
    <div v-else class="px-20 w-full flex flex-wrap">
      <div v-for="(card, i) in photoFeed" :key="i" class="w-1/5">
        <div class="w-full p-2">
          <Card
            class="w-full h-full"
            :src="`${card.download_url}`"
            :board="`${card.author}`"
          />
          <div class="text-sm leading-tight pt-2">
            <p>{{ card.id }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TopNav from "@/components/TopNav";
import Card from "@/components/Card";
import Loader from "@/components/Loader";
import axios from "axios";
export default {
  name: "App",
  components: {
    Card,
    TopNav,
    Loader,
  },
  data() {
    return {
      authorNameSearchString: "",
      photoFeed: null,
      loading: true,
    };
  },
  mounted() {
    axios
      .get("https://picsum.photos/v2/list?page=2&limit=30")
      .then((response) => {
        this.photoFeed = response.data;
        this.loading = false;
      })
      .catch((error) => console.log(error));
  },
};
</script>

<style></style>
