<template>
  <div id="Benifit" class="flex">
    <div class="benifit-left">
      <PageTitle :title="'Benifit'" />
      <div class="benifit-left__infos">
        <h3 class="benifit-left__infos--title">
          Benefit You Get When Using Our Services
        </h3>
        <div class="benifit-left__infos--card">
          <h3>600+</h3>
          <p>Home Furniture throughout Indonesia</p>
        </div>
        <div class="benifit-left__infos--card">
          <h3>135+</h3>
          <p>Staff ready to help you</p>
        </div>
      </div>
    </div>
    <div class="benifit-right flex">
      <BenifitCard
        v-for="card, i in cards"
        :key="i"
        :icon="card.icon"
        :title="card.title"
        :description="card.description"
      />
    </div>
  </div>
</template>

<script>
import BenifitCard from "./BenifitCard.vue";
import PageTitle from "./PageTitle.vue";
export default {
  components: { PageTitle, BenifitCard },
  data: () => ({
    cards: [
      {
        icon: "HomeIcon",
        title: "Best Quality",
        description:
          "All of our funiture uses the best materials and choices for our customers.",
      },
      {
        icon: "WeckerIcon",
        title:
          "All of our funiture uses the best materials and choices for our customers.",
        description:
          "All of our funiture uses the best materials and choices for our customers.",
      },
      {
        icon: "CalendarIcon",
        title: "Space Customization",
        description:
          "All of our funiture uses the best materials and choices for our customers.",
      },
    ],
  }),
};
</script>