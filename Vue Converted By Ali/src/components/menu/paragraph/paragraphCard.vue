<template>
  <transition name="fade" mode="out-in">
    <div class="col-md-12 col-sm-12" :key="selectedHeader">
      <div class="toggle-content text-center">
        <h3>{{selectedHeader}}</h3>
        <p>
          {{ParagraphHeader}}
          <br />
          {{ParagraphBody}}
          <br />
          {{paragraphButtom}}
        </p>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  props: ["selectedHeader"],
  data() {
    return {
      ParagraphHeader: "You can easily change icons by Example:",
      ParagraphBody:
        "In varius eros ac est interdum In varius eros ac est interdum, quis scelerisque elit semper. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.",
      paragraphButtom:
        "Donec mattis enim sit amet nisl faucibus, eu pulvinar nibh facilisis. Aliquam erat volutpat. Vivamus tempus, nisi varius imperdiet molestie, velit mi feugiat felis, sit amet fringilla mi massa sit amet arcu. Mauris dictum nisl id felis lacinia congue. Aliquam lectus nisi, sodales in lacinia quis, lobortis vel sem. Vestibulum elit nisi, placerat eget auctor ut, dictum at libero.",
    };
  },
  methods: {
    getParagraphFromServer() {
      //mounted can be used as well
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