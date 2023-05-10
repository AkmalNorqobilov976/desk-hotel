<template>
  <div id="Recommendation">
    <PageTitle class="recommendation-title" title="Our Recommendation" />
    <div class="recommendation-head flex justify-space-between">
      <h3 class="recommendation-head__title">Featured House</h3>
      <div class="recommendation-head__filter-navigator flex">
        <div class="recommendation-head__filter-navigator--filter flex">
          <Btn
            v-for="(btn, i) in fltrs"
            :key="i"
            :color="'black'"
            :label="btn.title"
            :className="'row-reverse'"
            @click.native="onChangeHomeType(btn.title)"
            :class="{ active: homeType === btn.title }"
          >
            <template #icon>
              <component :is="btn.icon" />
            </template>
          </Btn>
        </div>
        <div
          class="recommendation-head__filter-navigator--navigator flex items-center"
        >
          <Btn class="button-prev">
            <template #icon>
              <ArrowLeftIcon />
            </template>
          </Btn>
          <Btn class="button-next">
            <template #icon>
              <ArrowRightIcon />
            </template>
          </Btn>
        </div>
      </div>
    </div>

    <div class="swiper mySwiper1">
      <div class="swiper-wrapper">
        <RecommendationCard
          class="swiper-slide slide_1"
          v-for="(card, i) in computedCards"
          :key="i"
          :title="card.title"
          :description="card.description"
          :userName="card.userName"
          :address="card.address"
          :btnLabel="card.btnLabel"
          :btnBgColor="card.btnBgColor"
          :btnColor="card.btnColor"
          :icon="card.icon"
          :userImage="card.userImage"
        >
          <template #image>
            <img :src="card.image" alt="" />
          </template>

          <template #userImage>
            <img :src="card.userImage" alt="" />
          </template>
        </RecommendationCard>
      </div>
    </div>
  </div>
</template>

<script>
import Btn from "./Btn.vue";
import PageTitle from "./PageTitle.vue";
import RecommendationCard from "./RecommendationCard.vue";
import { Swiper, Navigation } from "swiper";

export default {
  components: { PageTitle, Btn, RecommendationCard },
  mounted() {
    Swiper.use(Navigation);
    let swiper = new Swiper(".mySwiper1", {
      slidesPerView: 4,
      spaceBetween: 40,
      loop: true,
      centeredSlides: true,
      navigation: {
                nextEl: ".button-next",
        prevEl: ".button-prev",
      },
    });
    console.log(swiper);
  },
  data: () => ({
    homeType: "",
    fltrs: [
      {
        icon: "HouseIcon",
        title: "House",
      },
      {
        icon: "VillaIcon",
        title: "Villa",
      },
      {
        icon: "ApartmentIcon",
        title: "Apartment",
      },
    ],
    navigators: ["ArrowLeftIcon", "ArrowRightIcon"],
    cards: [
      {
        image: require("./../assets/images/home2.png"),
        title: "Woodlandside",
        description: "$ 20.000.000",
        userName: "Robert Fox",
        address: "Dr. San Jose, South Dakota",
        userImage: require("./../assets/images/human5.png"),
        btnLabel: "New house",
        btnBgColor: "#DBEAFE",
        btnColor: "#1D4ED8",
        icon: "HouseIcon",
        type: "House",
      },
      {
        image: require("./../assets/images/home3.png"),
        title: "The Old Lighthouse",
        description: "$ 44.000.000",
        userName: "Ronald Richards",
        address: "Santa Ana, Illinois",
        userImage: require("./../assets/images/human6.png"),
        btnLabel: "Best Deals",
        btnBgColor: "#D1FAE5",
        btnColor: "#047857",
        icon: "WalletIcon",
        type: "Villa",
      },
      {
        image: require("./../assets/images/home4.png"),
        title: "Cosmo's House",
        description: "$ 22.000.000",
        userName: "Jenny Wilson",
        address: "Preston Rd. Inglewood, Maine 98380",
        userImage: require("./../assets/images/human7.png"),
        btnLabel: "Popular",
        btnBgColor: "#FEE2E2",
        btnColor: "#EF4444",
        icon: "FireIcon",
        type: "Apartment",
      },
      {
        image: require("./../assets/images/home2.png"),
        title: "Woodlandside",
        description: "$ 20.000.000",
        userName: "Robert Fox",
        address: "Dr. San Jose, South Dakota",
        userImage: require("./../assets/images/human5.png"),
        btnLabel: "New house",
        btnBgColor: "#DBEAFE",
        btnColor: "#1D4ED8",
        icon: "HouseIcon",
        type: "House",
      },
      {
        image: require("./../assets/images/home3.png"),
        title: "The Old Lighthouse",
        description: "$ 44.000.000",
        userName: "Ronald Richards",
        address: "Santa Ana, Illinois",
        userImage: require("./../assets/images/human6.png"),
        btnLabel: "Best Deals",
        btnBgColor: "#D1FAE5",
        btnColor: "#047857",
        icon: "WalletIcon",
        type: "Villa",
      },
      {
        image: require("./../assets/images/home4.png"),
        title: "Cosmo's House",
        description: "$ 22.000.000",
        userName: "Jenny Wilson",
        address: "Preston Rd. Inglewood, Maine 98380",
        userImage: require("./../assets/images/human7.png"),
        btnLabel: "Popular",
        btnBgColor: "#FEE2E2",
        btnColor: "#EF4444",
        icon: "FireIcon",
        type: "Apartment",
      },
      {
        image: require("./../assets/images/home2.png"),
        title: "Woodlandside",
        description: "$ 20.000.000",
        userName: "Robert Fox",
        address: "Dr. San Jose, South Dakota",
        userImage: require("./../assets/images/human5.png"),
        btnLabel: "New house",
        btnBgColor: "#DBEAFE",
        btnColor: "#1D4ED8",
        icon: "HouseIcon",
        type: "House",
      },
      {
        image: require("./../assets/images/home3.png"),
        title: "The Old Lighthouse",
        description: "$ 44.000.000",
        userName: "Ronald Richards",
        address: "Santa Ana, Illinois",
        userImage: require("./../assets/images/human6.png"),
        btnLabel: "Best Deals",
        btnBgColor: "#D1FAE5",
        btnColor: "#047857",
        icon: "WalletIcon",
        type: "Villa",
      },
      {
        image: require("./../assets/images/home4.png"),
        title: "Cosmo's House",
        description: "$ 22.000.000",
        userName: "Jenny Wilson",
        address: "Preston Rd. Inglewood, Maine 98380",
        userImage: require("./../assets/images/human7.png"),
        btnLabel: "Popular",
        btnBgColor: "#FEE2E2",
        btnColor: "#EF4444",
        icon: "FireIcon",
        type: "Apartment",
      },
      {
        image: require("./../assets/images/home2.png"),
        title: "Woodlandside",
        description: "$ 20.000.000",
        userName: "Robert Fox",
        address: "Dr. San Jose, South Dakota",
        userImage: require("./../assets/images/human5.png"),
        btnLabel: "New house",
        btnBgColor: "#DBEAFE",
        btnColor: "#1D4ED8",
        icon: "HouseIcon",
        type: "House",
      },
      {
        image: require("./../assets/images/home3.png"),
        title: "The Old Lighthouse",
        description: "$ 44.000.000",
        userName: "Ronald Richards",
        address: "Santa Ana, Illinois",
        userImage: require("./../assets/images/human6.png"),
        btnLabel: "Best Deals",
        btnBgColor: "#D1FAE5",
        btnColor: "#047857",
        icon: "WalletIcon",
        type: "Villa",
      },
      {
        image: require("./../assets/images/home4.png"),
        title: "Cosmo's House",
        description: "$ 22.000.000",
        userName: "Jenny Wilson",
        address: "Preston Rd. Inglewood, Maine 98380",
        userImage: require("./../assets/images/human7.png"),
        btnLabel: "Popular",
        btnBgColor: "#FEE2E2",
        btnColor: "#EF4444",
        icon: "FireIcon",
        type: "Apartment",
      },
      {
        image: require("./../assets/images/home2.png"),
        title: "Woodlandside",
        description: "$ 20.000.000",
        userName: "Robert Fox",
        address: "Dr. San Jose, South Dakota",
        userImage: require("./../assets/images/human5.png"),
        btnLabel: "New house",
        btnBgColor: "#DBEAFE",
        btnColor: "#1D4ED8",
        icon: "HouseIcon",
        type: "House",
      },
      {
        image: require("./../assets/images/home3.png"),
        title: "The Old Lighthouse",
        description: "$ 44.000.000",
        userName: "Ronald Richards",
        address: "Santa Ana, Illinois",
        userImage: require("./../assets/images/human6.png"),
        btnLabel: "Best Deals",
        btnBgColor: "#D1FAE5",
        btnColor: "#047857",
        icon: "WalletIcon",
        type: "Villa",
      },
      {
        image: require("./../assets/images/home4.png"),
        title: "Cosmo's House",
        description: "$ 22.000.000",
        userName: "Jenny Wilson",
        address: "Preston Rd. Inglewood, Maine 98380",
        userImage: require("./../assets/images/human7.png"),
        btnLabel: "Popular",
        btnBgColor: "#FEE2E2",
        btnColor: "#EF4444",
        icon: "FireIcon",
        type: "Apartment",
      },
    ],
  }),
  computed: {
    computedCards: {
      get() {
        if (!this.homeType) {
          return this.cards;
        }
        return this.cards.filter((card) => card.type == this.homeType);
      },
    },
  },
  methods: {
    onChangeHomeType(homeType) {
      this.homeType = homeType;
    },
  },
};
</script>