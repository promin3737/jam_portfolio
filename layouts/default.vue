<!-- layouts/default.vue -->
<template>
  <div class="font-main flex flex-wrap justify-around">
    <header class="w-64 h-64">
      <div class="w-64 mt-24 ml-2 relative md:fixed">
        <div class="flex">
          <div
            class="bg-center bg-cover w-16 h-16 mr-2 rounded-full shadow photo"
          ></div>
          <div>
            <h1 class="font-bold">Shunsuke Sanada</h1>
            <p class="text-xs text-justify">
              関西学院大学 総合政策学部 メディア情報学科３年の真田
              隼輔です。Vue.js,Nuxt.js,Ruby on
              Railsを中心に空き時間にアプリ開発を行なっています。
            </p>
          </div>
        </div>
        <div class="flex justify-around mt-5 text-xs">
          <!-- <nuxt-link to="https://www.instagram.com/hayabusa_3737/">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faCode" />
              </fa-layers>
              Instagram
            </button>
          </nuxt-link> -->
          <a href="https://twitter.com/hayabusa_3737" target="_blank" rel="noopener noreferrer">
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faTwitter" />
              </fa-layers>
              Twitter
            </button>
          </a>
          <a
            href="https://github.com/promin3737"
            target="_blank"
            rel="noopener noreferrer"
          >
            <button>
              <fa-layers full-width class="fa-2x block mx-auto mb-1">
                <fa :icon="faGithub" />
              </fa-layers>
              GitHub
            </button>
          </a>
        </div>
        <input type="text" placeholder="Keywords" class="bg-gray-300 p-2 text-xs rounded w-full mt-5 focus:outline-none" v-model="keyword" @keypress.enter="$router.push('/search/' + keyword)">
      </div>
    </header>
    <main class="w-full mt-10">
      <nuxt />
    </main>
  </div>
</template>

<script>
import { faTwitter } from "@fortawesome/free-brands-svg-icons";
import { faGithub } from "@fortawesome/free-brands-svg-icons";
import { faCode } from "@fortawesome/free-solid-svg-icons";
export default {
  data() {
    return {
      keyword: ''
    }
  },
  computed: {
    faTwitter() {
      return faTwitter;
    },
    faGithub() {
      return faGithub;
    },
    faCode() {
      return faCode;
    }
  }
};
</script>

<style>
main {
  max-width: 550px;
}
.photo {
  min-width: 4rem;
  min-height: 4rem;
  background-image: url("assets/my-profile.JPG");
}
button:focus {
  outline: none;
}
</style>
