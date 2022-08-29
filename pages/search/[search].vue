<template>
  <div class="search-page">
    <p v-if="!results.length" class="text-2xl px-4">No Results.</p>
    <div v-else>
      <p class="text-2xl px-4">Search Results for "{{ url }}":</p>
      <div class="animes grid col-auto rows-auto mt-6 mx-auto">
        <nuxt-link
          :nuxt-child-key="anime.id"
          :to="`/anime/` + anime.slug"
          v-for="(anime, index) in results"
        >
          <anime-card
            :key="anime.id"
            :id="anime.id"
            :slug="anime.slug"
            :coverImage="anime.coverImage"
            :status="anime.status"
            :title="anime.title"
            :currentEpisode="anime.currentEpisode"
          />
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "#imports";
import { useFetch, useRoute, useRuntimeConfig } from "#app";
import { createError } from "h3";

const runtimeConfig = useRuntimeConfig();
const route = useRoute();
const url = `${route.params.search}`;
const results = ref([]);

const { error, data } = await useFetch(
  `${runtimeConfig.public.enimeApi}/search/${url}?perPage=10`,
  {
    key: url,
  }
);

if (error.value)
  throw createError({ statusCode: 429, message: "Too many requests" });

if (data.value) results.value = data.value.data;

//console.log(`${runtimeConfig.public.enimeApi}/search/${url}?perPage=10`, results.value);
</script>

<script lang="ts">
export default {
  name: "search-page",
};
</script>

<style scoped lang="scss">
.text-2xl {
  width: full;
  max-width: 1566px;
  margin: auto;
}
.animes {
  grid-template-columns: repeat(auto-fill, minmax(21rem, 1fr));
  //grid-template-rows: min-content;
  column-gap: 1.25rem;
  margin-right: 2vw;
  margin-left: 2vw;
}
</style>