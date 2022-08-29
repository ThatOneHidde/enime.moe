<template>
  <div class="dark:bg-[#17171A] text-white h-screen w-screen">
    <div
      class="
        flex flex-row
        max-w-[1566px]
        px-4
        w-full
        h-[70px]
        m-auto
        items-center
        justify-between
      "
    >
      <button @click="mobileMenu = !mobileMenu" class="lg:hidden mr-2 mb-1">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          x="0px"
          y="0px"
          width="30"
          height="30"
          viewBox="0 0 172 172"
          style="fill: #000000"
        >
          <g
            fill="none"
            fill-rule="nonzero"
            stroke="none"
            stroke-width="1"
            stroke-linecap="butt"
            stroke-linejoin="miter"
            stroke-miterlimit="10"
            stroke-dasharray=""
            stroke-dashoffset="0"
            font-family="none"
            font-weight="none"
            font-size="none"
            text-anchor="none"
            style="mix-blend-mode: normal"
          >
            <path d="M0,172v-172h172v172z" fill="none"></path>
            <g fill="#ffffff">
              <path
                d="M17.2,40.13333c-2.06765,-0.02924 -3.99087,1.05709 -5.03322,2.843c-1.04236,1.78592 -1.04236,3.99474 0,5.78066c1.04236,1.78592 2.96558,2.87225 5.03322,2.843h137.6c2.06765,0.02924 3.99087,-1.05709 5.03322,-2.843c1.04236,-1.78592 1.04236,-3.99474 0,-5.78066c-1.04236,-1.78592 -2.96558,-2.87225 -5.03322,-2.843zM17.2,80.26667c-2.06765,-0.02924 -3.99087,1.05709 -5.03322,2.843c-1.04236,1.78592 -1.04236,3.99474 0,5.78066c1.04236,1.78592 2.96558,2.87225 5.03322,2.843h137.6c2.06765,0.02924 3.99087,-1.05709 5.03322,-2.843c1.04236,-1.78592 1.04236,-3.99474 0,-5.78066c-1.04236,-1.78592 -2.96558,-2.87225 -5.03322,-2.843zM17.2,120.4c-2.06765,-0.02924 -3.99087,1.05709 -5.03322,2.843c-1.04236,1.78592 -1.04236,3.99474 0,5.78066c1.04236,1.78592 2.96558,2.87225 5.03322,2.843h137.6c2.06765,0.02924 3.99087,-1.05709 5.03322,-2.843c1.04236,-1.78592 1.04236,-3.99474 0,-5.78066c-1.04236,-1.78592 -2.96558,-2.87225 -5.03322,-2.843z"
              ></path>
            </g>
          </g>
        </svg>
      </button>
      <div class="flex flex-row gap-12 w-full">
        <router-link to="/" class="text-2xl md:text-4xl font-bold"
          >Enime</router-link
        >
        <nav
          class="
            hidden
            lg:flex
            flex-row
            w-auto
            justify-between
            items-center
            gap-6
          "
        >
          <router-link
            to="/"
            class="text-lg whitespace-nowrap text-[#ccc]"
            exact
            >All</router-link
          >
          <nuxt-link class="text-lg whitespace-nowrap text-[#ccc]" exact
            >Movies</nuxt-link
          >
          <nuxt-link class="text-lg whitespace-nowrap text-[#ccc]" exact
            >Tv-Shows</nuxt-link
          >
          <nuxt-link
            to="https://github.com/Enime-Project"
            class="text-lg whitespace-nowrap text-[#ccc]"
            exact
            >GitHub</nuxt-link
          >
          <nuxt-link to="" class="text-lg whitespace-nowrap text-[#ccc]" exactw
            >Donate</nuxt-link
          >
        </nav>
        <div class="hidden md:grid w-full max-w-100">
          <div
            class="
              urmom
              text-tertiary
              flex flex-row flex-nowrap
              items-center
              px-4
            "
          >
            <svg
              width="1rem"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="4"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
              />
            </svg>
            <span class="ez pl-1 text-lg mt-[1px]">Search</span>
          </div>
          <input
            @keyup.enter="search"
            ref="search"
            placeholder=" "
            class="urmom in p-1 pl-4 rounded-full pr-4"
          />
        </div>
      </div>
      <button
        class="ml-12 w-12 h-12"
        v-on:click="say('This feature is in developent!')"
      >
        <img src="../public/images/pfp.png" class="rounded-full" />
      </button>
    </div>
    <div v-show="mobileMenu" class="lg:hidden">
      <nav class="flex flex-col w-auto justify-between gap-6 pl-4">
        <router-link to="/" class="text-lg whitespace-nowrap text-[#ccc]" exact
          >All</router-link
        >
        <nuxt-link class="text-lg whitespace-nowrap text-[#ccc]" exact
          >Movies</nuxt-link
        >
        <nuxt-link class="text-lg whitespace-nowrap text-[#ccc]" exact
          >Tv-Shows</nuxt-link
        >
        <nuxt-link
          to="https://github.com/Enime-Project"
          class="text-lg whitespace-nowrap text-[#ccc]"
          exact
          >GitHub</nuxt-link
        >
        <nuxt-link to="" class="text-lg whitespace-nowrap text-[#ccc]" exactw
          >Donate</nuxt-link
        >
        <div class="md:hidden grid w-full max-w-100">
          <div
            class="
              urmom
              text-tertiary
              flex flex-row flex-nowrap
              items-center
              px-4
            "
          >
            <svg
              width="1rem"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="4"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
              />
            </svg>
            <span class="ez pl-1 text-lg mt-[1px]">Search</span>
          </div>
          <input
            @keyup.enter="search2"
            ref="search2"
            placeholder=" "
            class="urmom in p-1 pl-4 rounded-full pr-4"
          />
        </div>
      </nav>
    </div>
    <div class="flex-grow w-screen p-0 m-0">
      <slot />
    </div>
    <footer class="dark:bg-[#17171A] py-10">
      <div class="foot-cont flex flex-row content-between mx-auto">
        <div class="disclaimer">
          <div class="flex flex-row items-center mb-3">
            <img src="/icons/64x64.png" class="w-6 mr-2" />
            <h1 class="text-2xl">Enime-Project</h1>
          </div>
          <p class="gray-text">
            ENIME.MOE is not affiliated with or endorsed by any of the anime
            studios behind the creation of the anime presented on this site.
            This website is only an user interface presenting/linking various
            self-hosted files across the internet by other third-party providers
            for easy access.
            <br />
            © ENIME.MOE {{ new Date().getFullYear() }} | Built with
            <a
              href="https://github.com/Enime-Project/api.enime.moe"
              target="_blank"
              class="text-tertiary"
              >Enime API</a
            >
          </p>
        </div>
        <div class="flex-1 flex items-center justify-end">
          <a target="_blank" href="https://github.com/Enime-Project/enime.moe"
            ><img class="h-7 mr-5" src="/icons/github.png"
          /></a>
          <a target="_blank" href="https://discord.gg/nxr8be8WGa"
            ><img class="w-7" src="/icons/discord.png"
          /></a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script lang="ts">
import { navigateTo } from "#app";

export default {
  name: "default",
  methods: {
    search(e) {
      let search = this.$refs.search.value.trim();
      if (search.length > 1) navigateTo(`/search/${search}`);
    },
    search2(e) {
      let search = this.$refs.search2.value.trim();
      if (search.length > 1) navigateTo(`/search/${search}`);
    },
    say: function (message) {
      alert(message);
    },
    showMobileMenu() {
      this.$emit("showMobileMenu");
    },
  },
  data() {
    return {
      mobileMenu: false,
    };
  },
};
</script>

<style scoped lang="scss">
.nuxt-link-active {
  color: white !important;
  font-weight: bold;
}
.nuxt-link-exact-active {
  color: white !important;
  font-weight: bold;
}
.foot-cont {
  margin: 0 10vw;
}

.urmom {
  grid-column: 1;
  grid-row: 1;
}
.in {
  background-color: transparent; /* #fff3; */
  border: 1px solid #999;

  &:not(:placeholder-shown) {
    background-color: black;
  }
  &:focus {
    // border: 3px solid #999;
    outline: none;
  }
}
.disclaimer {
  flex: 3;
}
.gray-text {
  color: #ccc;
}
</style>