<template>
  <div id="menu-2" class="services content">
    <div class="row">
      <ul class="tabs">
        <li class="col-md-4 col-sm-4" v-for="(icon,index) in icons" :key="index">
          <a
            href="#"
            :class="`icon-item ${index==0? 'active':''}`"
            @click="activeclass(icon,index)"
          >
            <i :class="`fa fa-${icon}`"></i>
          </a>
        </li>
      </ul>
      <paragraphCard :selectedHeader="selectedHeader" />
      <!-- /.tabs -->
    </div>
  </div>
</template>

<script>
import paragraphCard from "./paragraph/paragraphCard.vue";

export default {
  components: {
    paragraphCard,
  },
  data() {
    return {
      icons: ["cogs", "leaf", "users"],
      paragraphHeaders: ["OUR SERVICES", "OUR SUPPORT", "TESTIMONIALS"],
      selectedHeader: "OUR SERVICES",
    };
  },
  methods: {
    activeclass(clicked, index) {
      for (const count of this.icons) {
        $(`.fa-${count}`).parent().removeClass("active");
      }
      $(`.fa-${clicked}`).parent().addClass("active");
      this.selectedHeader = this.paragraphHeaders[index];
    },
  },
};
</script>

<style>
</style>