<template>
  <Section :sectionName="sectionName">
    <div class="w-full">
      <div
        class="grid grid-cols-1 grid-rows-3 md:grid-cols-7 md:grid-rows-4 md:gap-x-8 gap-y-8"
      >
        <div class="md:col-start-1 md:col-span-3 md:row-span-2">
          <Card
            :title="'HelixScripts'"
            :routeLink="'helix-scripts'"
            :usedTechnologies="[
              'JavaScript',
              'Vue.js',
              'HTML',
              'Python',
              'Flask',
              'Webpack',
            ]"
          >
            Automated checkout solution for different online stores
          </Card>
        </div>
        <div class="md:col-start-5 md:col-span-3 md:row-start-2 md:row-span-2">
          <Card
            :title="'Accounting script'"
            :usedTechnologies="['Python', 'Stripe API', 'sevDesk API']"
            :gitUrl="
              'https://github.com/Fabio-GitHub25/stripe_sevdesk_accounting_script'
            "
          >
            Automated booking of stripe payout invoices in sevDesk
          </Card>
        </div>
        <div class="md:col-start-2 md:col-span-3 md:row-span-2">
          <Card
            :title="'Image uploader'"
            :usedTechnologies="['Node.js', 'Discord.js', 'Twitter API']"
            :gitUrl="
              'https://github.com/Fabio-GitHub25/discord_twitter_image_uploader'
            "
          >
            Automatic image uploader from Discord to Twitter
          </Card>
        </div>
      </div>
    </div>
  </Section>
</template>
<script>
import Section from "../Section.vue";
import Card from "./Card.vue";
export default {
  components: {
    Section,
    Card,
  },
  props: {
    sectionName: {
      type: String,
      required: true,
    },
  },
};
</script>
