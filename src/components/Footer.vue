<template>
  <footer id="footer">
    <div class="container footer-shell">
      <div class="footer-brand">
        <img src="@/assets/img/logo_white.png" alt="logo图">
        <h3>成都云从本图科技有限公司</h3>
        <p>提供软件定制、AI 应用开发、官网建设与 IT 外包服务。</p>
      </div>

      <div class="footer-links">
        <h4>快速访问</h4>
        <router-link to="/home">首页</router-link>
        <router-link to="/service">我们的服务</router-link>
        <router-link to="/companyintroduction">公司介绍</router-link>
        <router-link to="/contactus">联系我们</router-link>
      </div>

      <div class="footer-contact">
        <h4>联系方式</h4>
        <p>电话：18200280142</p>
        <p>地址：中国（四川）自由贸易试验区成都高新区交子北一路88号1栋2单元14层1413号</p>
      </div>
    </div>

    <div class="footer-copy">
      Copyright &copy; 2024 - {{ new Date().getFullYear() }} 成都云从本图科技有限公司
      <a href="https://beian.miit.gov.cn/" target="_blank">蜀ICP备2024094724号-3</a>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style scoped>
#footer {
  margin-top: 24px;
  color: rgba(255, 255, 255, 0.8);
  background: #111827;
}

.footer-shell {
  display: grid;
  grid-template-columns: 1.4fr 0.8fr 1fr;
  gap: 40px;
  padding: 56px 0 32px;
}

.footer-brand img {
  width: 74px;
  margin-bottom: 16px;
}

.footer-brand h3,
.footer-links h4,
.footer-contact h4 {
  margin: 0 0 16px;
  color: #fff;
}

.footer-brand p,
.footer-contact p {
  margin: 0;
  line-height: 1.9;
}

.footer-links a {
  display: block;
  margin-bottom: 12px;
  color: rgba(255, 255, 255, 0.78);
  text-decoration: none;
}

.footer-links a:hover,
.footer-copy a:hover {
  color: #fff;
  text-decoration: none;
}

.footer-copy {
  padding: 18px 16px 26px;
  color: rgba(255, 255, 255, 0.62);
  text-align: center;
  border-top: 1px solid rgba(255, 255, 255, 0.08);
}

.footer-copy a {
  margin-left: 6px;
  color: rgba(255, 255, 255, 0.78);
  text-decoration: none;
}

@media screen and (max-width: 997px) {
  .footer-shell {
    grid-template-columns: 1fr;
    gap: 28px;
    padding: 40px 0 24px;
  }
}
</style>

