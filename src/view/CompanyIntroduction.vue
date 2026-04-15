<template>
  <div id="CompanyIntroduction">
    <section class="intro-hero">
      <div class="container">
        <span class="section-eyebrow">About Us</span>
        <h1>以业务价值为导向的数字化服务团队</h1>
        <p>
          成都云从本图科技有限公司专注于软件定制、官网建设、AI 应用开发与技术外包，
          帮助企业建立可持续的数字化能力。
        </p>
      </div>
    </section>

    <section class="intro-content">
      <div class="container">
        <div class="intro-card row">
          <div class="col-xs-12 col-md-6 wow fadeInLeft">
            <div class="visual-shell">
              <img class="img-responsive center-block" src="@/assets/img/about_img.png" alt="公司介绍">
            </div>
          </div>
          <div class="col-xs-12 col-md-6 wow fadeInRight">
            <h2>成都云从本图科技有限公司</h2>
            <p>
              我们是一家以科技创意为核心的技术服务公司，聚集软件开发、交互设计和 AI
              场景落地方面的复合型人才，致力于为企业提供更务实、更稳定的数字化解决方案。
            </p>
            <p>
              通过持续的服务实践，我们帮助客户在效率、成本和市场表现上实现可衡量提升。
              未来也将继续坚持专业、创新、务实的服务理念，为更多企业提供高质量交付。
            </p>
            <div class="tag-list">
              <span>专业交付</span>
              <span>长期协作</span>
              <span>AI落地能力</span>
              <span>业务导向设计</span>
            </div>
          </div>
        </div>

        <div class="value-grid row">
          <div class="col-xs-12 col-sm-6 col-md-3" v-for="(item, index) in valueList" :key="index">
            <div class="value-item wow fadeInUp" :data-wow-delay="index * 0.1 + 's'">
              <strong>0{{ index + 1 }}</strong>
              <h3>{{ item.title }}</h3>
              <p>{{ item.content }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import { WOW } from 'wowjs';
export default {
  name: "CompanyIntroduction",
  data() {
    return {
      valueList: [
        {
          title: "需求导向",
          content: "先理解业务和目标，再定义产品方案和技术路径。"
        },
        {
          title: "设计与开发协同",
          content: "视觉、交互与开发同步推进，减少沟通损耗。"
        },
        {
          title: "稳定交付",
          content: "分阶段推进，确保质量、进度与上线可控。"
        },
        {
          title: "持续优化",
          content: "上线后持续迭代，提升系统长期价值。"
        }
      ]
    };
  },
  mounted() {
    var wow = new WOW();
    wow.init();
  }
};
</script>
<style scoped>
#CompanyIntroduction {
  background: #f7f9fc;
}

.section-eyebrow {
  display: inline-block;
  margin-bottom: 16px;
  color: #4f6bff;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 1.5px;
  text-transform: uppercase;
}

.intro-hero {
  padding: 72px 0 24px;
}

.intro-hero h1 {
  margin: 0 0 16px;
  color: #111827;
  font-size: 42px;
}

.intro-hero p,
.intro-card p,
.value-item p {
  color: #5b6475;
  line-height: 1.9;
}

.intro-content {
  padding: 8px 0 80px;
}

.intro-card {
  margin: 0;
  padding: 36px;
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 28px;
  box-shadow: 0 18px 42px rgba(15, 23, 42, 0.05);
}

.visual-shell {
  padding: 22px;
  background: linear-gradient(180deg, #f4f7ff, #eef3ff);
  border-radius: 24px;
}

.intro-card h2 {
  margin: 4px 0 14px;
  color: #111827;
  font-size: 32px;
}

.tag-list {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 20px;
}

.tag-list span {
  padding: 10px 14px;
  color: #3d4a63;
  background: #f3f6fb;
  border-radius: 999px;
  font-size: 13px;
}

.value-grid {
  margin: 26px 0 0;
}

.value-item {
  height: 100%;
  padding: 24px;
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 22px;
  box-shadow: 0 16px 36px rgba(15, 23, 42, 0.04);
}

.value-item strong {
  color: #4f6bff;
  font-size: 28px;
}

.value-item h3 {
  margin: 10px 0 12px;
  color: #111827;
  font-size: 20px;
}

@media screen and (max-width: 997px) {
  .intro-hero h1,
  .intro-card h2 {
    font-size: 32px;
  }

  .intro-card {
    padding: 24px;
  }
}

@media screen and (max-width: 767px) {
  .intro-hero {
    padding-top: 64px;
  }

  .intro-hero h1,
  .intro-card h2 {
    font-size: 28px;
  }

  .intro-content {
    padding-bottom: 56px;
  }
}
</style>

