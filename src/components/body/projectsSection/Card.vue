<template>
    <div
      @mouseover="isActiveText = true"
      @mouseleave="isActiveText = false"
      class="w-full h-full md:h-auto border pt-2 border-white rounded lg:max-w-full lg:flex bg-darker shadow-md duration-500 relative"
    >
      <div class="w-full border-b border-white mt-5 absolute"></div>
      <div
        class="rounded-b lg:rounded-b-none lg:rounded-r pt-4 px-4 flex flex-col justify-between leading-normal"
      >
        <div class="pt-5">
          <div :class="isActiveText ? 'duration-500 font-bold text-xl my-2 text-main' : 'duration-500 font-bold text-xl my-2'">{{ title }}</div>
          <span class="text-dark-text text-sm sm:text-base">
            <slot />
          </span>
        </div>
        <div class="md:pb-5 pb-2 text-sm mt-3">
          <span
            v-for="(technologie, key) of usedTechnologies"
            :key="`Tech-${title}-${key}`"
            class="inline-block sm:text-xs text-xxs mt-2 font-semibold px-2 pt-0.5 rounded border align-middle mr-2"
          >
            {{ technologie }}
          </span>
        </div>
        <span class="absolute right-3 top-1 cursor-pointer">
          <router-link
            v-if="routeLink"
            :to="`blog/${routeLink}`"
          >
            <font-awesome-icon
              icon="fa fa-pen"
              class="ml-2 duration-500 hover:text-main"
            />
            <!-- <i class=" sm:fa-lg duration-500 hover:text-main"></i> -->
          </router-link>
          <a
            v-if="gitUrl"
            :href="gitUrl"
            target="_blank"
          >
            <font-awesome-icon
              icon="fa-brands fa-github"
              class="ml-2 duration-500 hover:text-main"
            />
            <!-- <i class=" sm:fa-lg "></i> -->
          </a>
          <a 
            v-if="externalPageUrl"
            :href="externalPageUrl"
            target="_blank"
          >
            <font-awesome-icon
              icon="fa-solid fa-arrow-up-right-from-square"
              class="ml-2 duration-500 hover:text-main"
            />
            <!-- <i class=" sm:fa-lg ml-2 duration-500 hover:text-main"></i> -->
          </a>
        </span>
      </div>
    </div>
</template>
<script>

export default {
  props: {
    title: {
      type: String,
      required: true
    },
    usedTechnologies: {
      type: Array,
      required: true
    },
    routeLink: {
      type: String,
      default: null
    },
    gitUrl: {
      type: String,
      default: null
    },
    externalPageUrl: {
      type: String,
      default: null,
    }
  },
  data: function() {
    return {
      isActiveText: false,
    };
  },
};
</script>
