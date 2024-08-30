<template>
  <div id="JobChance">
    <div class="banner container-fuild text-center">工作机会</div>
    <div class="container">
      <div class="JobChance-container wow pulse">
        <h2>前端开发工程师</h2>
        <p>岗位职责</p>
        <ol>
          <li>负责公司Web前端、微信小程序开发项目的设计、开发和维护；</li>
          <li>与产品、后端、测试、设计等多个协作方通力合作,以达成业务目标为导向,高效高质量的完成所交付的前端开发工作</li>
          <li>对网站性能负责,高度关注性能指标,及时发现性能问题,快速定位性能瓶颈,制定优化方案并推进解决</li>
        </ol>
        <p>任职要求</p>
        <ol>
          <li>本科及以上学历,2年以上前端开发经验</li>
          <li>精通 HTML5、CSS3、JavaScript/TypeScript等前端技术栈</li>
          <li>熟悉Vue.js 2.x和3.x,Nuxt.js 2.x和3.x的开发和应用</li>
          <li>熟悉微信小程序的开发和应用</li>
          <li>深入理解浏览器渲染原理、事件机制、网络请求等前端基础知识</li>
          <li>拥有良好的架构设计能力和编码能力/编码风格,熟悉业界开发最优实践,6能编写可维护、可读性强、简洁易懂的高质量代码</li>
          <li>具有良好的沟通能力,能与产品经理、设计师等密切配合,心态上要比较开发和包容,不能闭门造车,需要懂得取舍和权衡利弊</li>
        </ol>
        <button class="center-block btn btn-warning btn-lg">投递简历</button>
      </div>
    </div>
  </div>
</template>
<script>
import { WOW } from 'wowjs';
export default {
  name: "JobChance",
  data() {
    return {};
  },
  mounted(){
    var wow = new WOW();
    wow.init();
  }
};
</script>
<style scoped>
.banner {
  color: #fff;
  font-size: 30px;
  height: 150px;
  line-height: 150px;
  background-image: url("../assets/img/banner_2.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: scroll;
  background-position: center center;
}
.JobChance-container {
  margin: 100px;
  padding: 30px;
  transition: all ease 0.5s;
  border: 1px dashed salmon;
}
.JobChance-container h2{
  color: rgb(255, 102, 19);
  font-weight: bolder;
  text-align: center;
}
.JobChance-container p{
font-size: 20px;
  color: rgb(255, 102, 19);
  font-weight: 700;
}
.JobChance-container ol{
    list-style-type: decimal;
    padding-left: 30px;
}
.JobChance-container ol>li{
    font-size: 14px;
    line-height: 2.7rem;
}
@media screen and (max-width: 997px) {
  .JobChance-container {
    margin: 20px 0;
    padding: 20px;
    border: 1px dashed salmon;
  }
}
</style>

