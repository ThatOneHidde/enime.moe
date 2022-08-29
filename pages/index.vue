<template>
  <div>
    <p class="font-bold text-2xl px-4">Recently Released</p>
    <client-only>
      <recent-release />
    </client-only>
  </div>
</template>

<script>
export default {
  name: "index",
};
</script>

<style>
</style>
<style scoped>
.text-2xl {
  width: full;
  max-width: 1566px;
  margin: auto;
}
</style>