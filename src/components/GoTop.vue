<template>
  <div id="GoTop" @click="GoTop()">
    <span class="glyphicon glyphicon-chevron-up"></span>
  </div>
</template>
<script>
export default {
  name: "GoTop",
  data() {
    return {
      flag: false
    };
  },
  methods: {
    GoTop() {
      (function smoothscroll() {
        var currentScroll =
          document.documentElement.scrollTop || document.body.scrollTop;
        if (currentScroll > 0) {
          window.requestAnimationFrame(smoothscroll);
          window.scrollTo(0, currentScroll - currentScroll / 10);
        }
      })();
    }
  }
};
</script>
<style scoped>
#GoTop {
  width: 48px;
  height: 48px;
  position: fixed;
  right: 24px;
  bottom: 24px;
  z-index: 1000;
  cursor: pointer;
  border-radius: 999px;
  background: linear-gradient(135deg, #4f6bff, #7a5cff);
  box-shadow: 0 16px 30px rgba(79, 107, 255, 0.24);
}
#GoTop > span {
  display: block;
  width: 100%;
  height: 100%;
  color: #fff;
  font-size: 18px;
  line-height: 48px;
  text-align: center;
}
</style>
