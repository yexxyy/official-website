<template>
  <div id="footer" class="container-fluid">
    <div class="logo">
      <img src="@/assets/img/logo_white.png" alt="logo图">
    </div>
    <!-- <p class="title">成都云从本图科技有限公司</p> -->
    
    <p class="email_wx">
      <span>邮箱：contect@heexin.cn</span>
      <!-- <span>微信号：xxx</span> -->
    </p>
    <p class="address_tel_fax">
      <span>地址：中国（四川）自由贸易试验区成都高新区交子北一路88号1栋2单元14层1413号</span>
      <!-- <span>Tel：888-888-888</span> -->
    </p>
    <p class="copy">Copyright &copy; 2024 - {{ new Date().getFullYear() }} 成都云从本图科技有限公司 <a href="https://beian.miit.gov.cn/" target="_blank" style="text-decoration:none; color: unset">蜀ICP备2024094724号-2</a></p>
  </div>
</template>
<script>
export default {
  name: "Footer",
  data() {
    return {};
  }
};
</script>
<style scoped>
#footer {
  width: 100%;
  height: 100%;
  color: #fff;
  background: #474747;
  overflow: hidden;
  text-align: center;
}
.logo {
  width: 95px;
  height: 45px;
  margin: 50px auto 20px;
}
.title {
  font-size: 25px;
  margin-bottom: 20px;
}
.address_tel_fax {
  color: #d3d3d3;
  font-size: 14px;
  margin: 10px 0;
}
.email_wx {
  color: #d3d3d3;
  font-size: 14px;
}
.copy {
  color: #d3d3d3;
  font-size: 14px;
}
@media screen and (max-width: 997px) {
  .title {
    font-size: 20px;
  }
  .address_tel_fax {
    font-size: 12px;
  }
  .email_wx {

  font-size: 12px;
}
.copy {
  font-size: 12px;
  margin: 30px 0 10px;
}
}
</style>

