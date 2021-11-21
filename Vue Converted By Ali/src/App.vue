<template>
  <div>
    <div class="container-fluid"></div>
    <MenuCard></MenuCard>
  </div>
</template>

<script>
import MenuCard from "./components/card.vue";
export default {
  components: {
    MenuCard,
  },
  mounted() {
    jQuery(function ($) {
      $.supersized({
        slide_interval: 3000,
        transition: 1,
        transition_speed: 700,
        // Components
        slide_links: "blank",
        slides: [
          {
            image: "/src/assets/images/templatemo-slide-1.jpg",
          },
          {
            image: "/src/assets/images/templatemo-slide-2.jpg",
          },
          {
            image: "/src/assets/images/templatemo-slide-3.jpg",
          },
          {
            image: "/src/assets/images/templatemo-slide-4.jpg",
          },
        ],
      });
    });
  },
};
</script>

<style scoped>
.container-fluid {
  padding: 60px 80px;
}

@media (max-width: 767px) {
  .container-fluid {
    padding: 20px;
  }
}
</style>
