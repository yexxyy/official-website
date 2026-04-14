<template>
  <header id="header">
    <div class="header-top hidden-xs">
      <div class="container top-inner">
        <span>欢迎咨询企业数字化、官网建设与 AI 应用开发</span>
        <span>服务热线：18200280142</span>
      </div>
    </div>

    <div class="container nav-shell">
      <router-link class="brand" to="/">
        <img src="@/assets/img/logo_black.png" alt="logo">
        <div>
          <strong>成都云从本图科技有限公司</strong>
          <span>Digital Product Studio</span>
        </div>
      </router-link>

      <nav class="nav-list hidden-xs">
        <router-link
          v-for="(item, index) in navList"
          :key="index"
          :to="item.path"
          :class="{ active: isActive(item.path) }"
        >
          {{ item.name }}
        </router-link>
      </nav>

      <router-link class="contact-btn hidden-xs" to="/contactus">立即咨询</router-link>

      <button class="menu-btn visible-xs" @click="menuOpen = !menuOpen">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>

    <div class="mobile-menu visible-xs" v-show="menuOpen">
      <router-link
        v-for="(item, index) in navList"
        :key="index"
        :to="item.path"
        @click.native="menuOpen = false"
      >
        {{ item.name }}
      </router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      menuOpen: false,
      navList: [
        { name: "首页", path: "/home" },
        { name: "我们的服务", path: "/service" },
        { name: "公司介绍", path: "/companyintroduction" },
        { name: "工作机会", path: "/jobchance" },
        { name: "联系我们", path: "/contactus" }
      ]
    };
  },
  methods: {
    isActive(path) {
      return this.$route.path === path;
    }
  },
  watch: {
    $route() {
      this.menuOpen = false;
    }
  }
};
</script>

<style scoped>
#header {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: rgba(247, 249, 252, 0.92);
  backdrop-filter: blur(14px);
  border-bottom: 1px solid rgba(17, 24, 39, 0.06);
}

.header-top {
  border-bottom: 1px solid rgba(17, 24, 39, 0.05);
}

.top-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  min-height: 42px;
  color: #667085;
  font-size: 12px;
}

.nav-shell {
  display: flex;
  align-items: center;
  justify-content: space-between;
  min-height: 84px;
}

.brand {
  display: flex;
  align-items: center;
  gap: 14px;
  color: #111827;
  text-decoration: none;
}

.brand:hover,
.nav-list a:hover,
.contact-btn:hover,
.mobile-menu a:hover {
  text-decoration: none;
}

.brand img {
  width: 54px;
  height: 54px;
  object-fit: contain;
}

.brand strong {
  display: block;
  font-size: 15px;
}

.brand span {
  color: #7c86a0;
  font-size: 12px;
}

.nav-list {
  display: flex;
  gap: 28px;
}

.nav-list a {
  position: relative;
  padding: 8px 0;
  color: #475467;
  font-size: 14px;
  font-weight: 600;
  text-decoration: none;
}

.nav-list a.active,
.nav-list a:hover {
  color: #4f6bff;
}

.nav-list a.active::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -8px;
  width: 100%;
  height: 2px;
  background: #4f6bff;
  border-radius: 999px;
}

.contact-btn {
  display: inline-block;
  padding: 12px 22px;
  color: #fff;
  background: linear-gradient(135deg, #4f6bff, #7a5cff);
  border-radius: 999px;
  font-size: 14px;
  font-weight: 600;
  text-decoration: none;
  box-shadow: 0 14px 28px rgba(79, 107, 255, 0.22);
}

.menu-btn {
  width: 44px;
  height: 44px;
  padding: 8px;
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.08);
  border-radius: 14px;
}

.menu-btn span {
  display: block;
  width: 100%;
  height: 2px;
  margin: 6px 0;
  background: #111827;
}

.mobile-menu {
  padding: 0 16px 16px;
}

.mobile-menu a {
  display: block;
  margin-top: 10px;
  padding: 14px 16px;
  color: #334155;
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 16px;
}

@media screen and (max-width: 767px) {
  .nav-shell {
    min-height: 72px;
  }

  .brand strong {
    font-size: 14px;
  }

  .brand span {
    display: none;
  }

  .brand img {
    width: 46px;
    height: 46px;
  }
}
</style>
