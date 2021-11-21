<template>
  <div id="menu-1" class="about content">
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
      <!-- /.tabs -->

      <div class="col-md-12 col-sm-12"></div>
      <paragraphCard :selectedHeader="selectedHeader"></paragraphCard>
      <transition name="fade" mode="out-in">
        <div class="row" :key="selectedHeader">
          <div class="col-md-4 col-sm-4" v-for="(icon,index) in names" :key="index">
            <div class="member-item">
              <div class="thumb">
                <img
                  :src="require(`../../assets/images/team/member-${index+1}.jpg`)"
                  alt="Tracy - Web Designer"
                />
              </div>
              <h4>{{icon}}</h4>
              <span>Web Designer</span>
            </div>
          </div>
          <!-- /.member-item -->
        </div>
      </transition>
    </div>
  </div>
  <!-- /.about -->
</template>

<script>
import paragraphCard from "./paragraph/paragraphCard.vue";

export default {
  components: {
    paragraphCard,
  },
  data() {
    return {
      icons: ["umbrella", "camera", "coffee"],
      names: ["TRACY", "MARY", "JULIA"],
      paragraphHeaders: ["OUR HISTORY", "WHAT WE DO", "OUR TEAM"],
      selectedHeader: "OUR HISTORY",
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


<style scoped>
.fade-enter {
  opacity: 0;
}

.fade-enter-active {
  transition: opacity 1.5s;
}
</style>