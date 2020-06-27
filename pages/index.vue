<template>
  <div class="container font-custom">
    <vue-flipcard ref="flipcard" :height="520" disable>
      <div
        slot="front"
        class="max-w-xs secondary-color text-black shadow-2xl rounded-lg overflow-hidden h-full"
        @click="onManualFlip"
      >
        <div class="grid grid-cols-1 h-full">
          <div class="absolute clip-hole bg-white shadow-inner"></div>
          <div class="flex">
            <div class="w-5/6">
              <div class="py-4 px-6 pt-20">
                <h1 class="text-5xl text-left font-semibold leading-none">IT / Backend Developer</h1>
                <div class="flex items-center justify-between my-12">
                  <svg height="100" width="60">
                    <circle
                      cx="30"
                      cy="30"
                      r="20"
                      stroke="black"
                      stroke-width="1"
                      fill="transparent"
                    />
                  </svg>
                  <div>
                    <h1 class="px-0 text-xs text-right font-light">Work at</h1>
                    <h1 class="px-0 text-sm text-right font-black">Female Daily</h1>
                  </div>
                </div>
                <h1 class="text-3xl text-left font-semibold leading-none">Alfian Rivaldi</h1>
                <div class="flex justify-around pt-5">
                  <a v-for="(link, i) in links" :key="i" :href="link.link">
                    <i :class="link.icon"></i>
                  </a>
                </div>
              </div>
            </div>
            <div class="w-1/6 primary-color">
              <h1
                class="text-white aside whitespace-no-wrap text-3xl ml-12 mt-5"
              >ABOUT ME</h1>
            </div>
          </div>
        </div>
      </div>
      <div
        slot="back"
        class="max-w-xs secondary-color text-black shadow-2xl rounded-lg overflow-hidden h-full"
        @click="onManualFlip"
      >
        <div class="grid grid-cols-1 h-full">
          <div class="absolute clip-hole bg-white shadow-inner"></div>
          <div class="flex">
            <div class="w-1/6 primary-color">
              <h1 class="text-white aside whitespace-no-wrap text-3xl ml-12 mt-5">MY SKILL</h1>
            </div>
            <div class="w-5/6">
              <div class="py-4 px-6 pt-20">
                <ul class="flex flex-col">
                  <li class="flex flex-row mb-3 items-center rounded-md p-2" v-for="(skill, i) in skills" :key="i">
                    <i class="text-4xl" :class="skill.icon"></i>
                    <h1 class="ml-2 text-xl">{{skill.name}}</h1>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </vue-flipcard>
  </div>
</template>

<script>
import VueFlipcard from "vue-flipcard";

export default {
  components: {
    "vue-flipcard": VueFlipcard
  },
  data() {
    return {
      links: [
        {
          link: "https://github.com/alfianriv",
          icon: "lni lni-github"
        },
        {
          link: "https://instagram.com/alfianriv",
          icon: "lni lni-instagram"
        },
        {
          link: "https://linkedin.com/in/alfianriv",
          icon: "lni lni-linkedin"
        },
        {
          link: "mailto:alfian.rivaldi8@gmail.com",
          icon: "lni lni-envelope"
        }
      ],
      skills: [
        {
          icon: 'lni lni-nodejs',
          name: 'NODEJS'
        },
        {
          icon: 'lni lni-database',
          name: "SQL & NOSQL"
        },
        {
          icon: 'lni lni-php',
          name: "PHP"
        },
        {
          icon: 'lni lni-javascript',
          name: "JAVASCRIPT"
        },
      ],
    };
  },
  methods: {
    onManualFlip() {
      this.$refs.flipcard.flip();
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Fjalla+One&display=swap");

.font-custom {
  font-family: "Fjalla One", sans-serif !important;
}

.primary-color {
  background-color: #192a56;
  background-image: url("https://www.transparenttextures.com/patterns/gplay.png");
}

.secondary-color {
  background-color: #c70039;
  background-image: url("https://www.transparenttextures.com/patterns/cartographer.png");
}

.clip-hole {
  left: 50%;
  margin-left: -90px;
  margin-top: 20px;
  border-radius: 25px;
  padding: 10px 7px;
  width: 180px;
  height: 10px;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.aside {
  position: absolute;
  background: none;
  transform-origin: 0 0;
  transform: rotate(90deg);
}
</style>
