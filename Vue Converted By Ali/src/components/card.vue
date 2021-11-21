<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-4 col-sm-12">
        <div class="sidebar-menu">
          <div class="menu-wrapper">
            <logoCard />
            <ul class="menu">
              <li>
                <a class="homebutton" href="#" @click="SlideWithHome">Home</a>
              </li>
              <li>
                <a class="show-1" href="#" @click="selectedComponent='aboutCard'">About</a>
              </li>
              <li>
                <a class="show-2" href="#" @click="selectedComponent='serviceCard'">Services</a>
              </li>
              <li>
                <a href="#" @click="selectedComponent='galleryCard'">Gallery</a>
              </li>
              <li>
                <a class="show-4" href="#" @click="selectedComponent='contactCard'">Contact</a>
              </li>
              <li>
                <a rel="nofollow" href="#">External Link</a>
              </li>
            </ul>
            <a href="#" class="toggle-menu" @click="toggleMenu">
              <i class="fa fa-bars"></i>
            </a>
          </div>

          <!--Arrow Navigation-->
          <a id="prevslide" class="load-item">
            <i class="fa fa-angle-left"></i>
          </a>
          <a id="nextslide" class="load-item">
            <i class="fa fa-angle-right"></i>
          </a>
        </div>
      </div>

      <div class="col-md-8 col-sm-12">
        <div id="menu-container">
          <transition name="fade" mode="out-in">
            <component :is="selectedComponent"></component>
          </transition>
        </div>
      </div>
    </div>
  </div>
</template>



<script>
import logoCard from "./logo.vue";
import aboutCard from "./menu/about.vue";
import serviceCard from "./menu/services.vue";
import galleryCard from "./menu/gallery.vue";
import contactCard from "./menu/contact.vue";

export default {
  data() {
    return {
      selectedComponent: "",
    };
  },
  components: {
    aboutCard,
    serviceCard,
    galleryCard,
    contactCard,
    logoCard,
  },
  props: {
    handleUserAction: {
      // type: Function,
    },
  },
  methods: {
    toggleMenu() {
      $(".menu").slideToggle(400);
      this.selectedComponent = "";
      return false;
    },
    SlideWithHome() {
      $(".menu").slideUp();
      this.selectedComponent = "";
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