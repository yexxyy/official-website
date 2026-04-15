<template>
  <div id="HomePage">
    <section class="hero-section">
      <div class="container hero-container">
        <div class="hero-copy wow fadeInUp">
          <span class="section-eyebrow">Digital Growth Partner</span>
          <h1>用更现代的数字产品，帮助企业建立增长能力</h1>
          <p>
            成都云从本图科技有限公司聚焦软件定制、AI 应用、官网商城建设与 IT
            外包，为企业提供从方案到交付的一体化技术服务。
          </p>
          <div class="hero-actions">
            <router-link class="primary-btn" to="/service">查看服务</router-link>
            <router-link class="ghost-btn" to="/contactus">联系我们</router-link>
          </div>
        </div>
        <div class="hero-panel wow fadeInRight">
          <div class="hero-card hero-card-primary">
            <p class="hero-card-label">核心方向</p>
            <h3>AI + 定制开发</h3>
            <p>把技术能力落到真实业务场景，兼顾效率、体验和后续扩展能力。</p>
          </div>
          <div class="hero-grid">
            <div
              class="hero-card hero-stat"
              v-for="(item, index) in statsList"
              :key="index"
            >
              <strong>{{ item.value }}</strong>
              <span>{{ item.label }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="company-section">
      <div class="container">
        <div class="row company-row">
          <div class="col-xs-12 col-md-6 wow fadeInLeft">
            <div class="company-visual">
              <img
                class="img-responsive center-block"
                src="@/assets/img/img1.png"
                alt="成都云从本图科技有限公司"
              >
            </div>
          </div>
          <div class="col-xs-12 col-md-6 wow fadeInRight">
            <span class="section-eyebrow">About Us</span>
            <h2>面向成长型企业的一站式技术服务团队</h2>
            <p>
              我们以科技创意为核心，为企业提供软件开发、网站建设、AI
              应用开发、IT 外包与移动端解决方案，帮助企业更高效地推进数字化建设。
            </p>
            <p>
              从业务梳理到产品落地，我们坚持用更清晰的方案、更稳定的交付和更务实的服务，
              帮助客户降低沟通成本、缩短上线周期并提升长期运营效率。
            </p>
            <div class="company-tags">
              <span>需求分析</span>
              <span>产品设计</span>
              <span>开发交付</span>
              <span>持续迭代</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="value-section">
      <div class="container">
        <div class="section-heading text-center">
          <span class="section-eyebrow">Why Choose Us</span>
          <h2>更简洁的协作方式，更稳定的交付体验</h2>
          <p>聚焦对企业真正有价值的功能与体验，减少冗余建设，提升落地效率。</p>
        </div>
        <div class="row">
          <div class="col-xs-12 col-sm-6 col-md-3" v-for="(item, index) in valueList" :key="index">
            <div class="value-card wow fadeInUp" :data-wow-delay="index * 0.1 + 's'">
              <span class="value-index">0{{ index + 1 }}</span>
              <h3>{{ item.title }}</h3>
              <p>{{ item.content }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="service-section">
      <div class="container">
        <div class="section-heading service-heading">
          <div>
            <span class="section-eyebrow">Our Services</span>
            <h2>围绕业务增长，提供更完整的服务内容</h2>
          </div>
          <router-link class="text-link" to="/service">查看全部服务</router-link>
        </div>
        <div class="row">
          <div class="col-xs-12 col-sm-6" v-for="(item, index) in serviceList" :key="index">
            <div class="service-card wow fadeInUp" @click="serviceClick(item.id)">
              <div class="service-card-copy">
                <span>{{ item.engTitle }}</span>
                <h3>{{ item.title }}</h3>
                <p>{{ item.summary }}</p>
                <ul>
                  <li v-for="(point, pointIndex) in item.highlights" :key="pointIndex">{{ point }}</li>
                </ul>
              </div>
              <div class="service-card-image">
                <img :src="item.image" :alt="item.title">
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="cta-section">
      <div class="container cta-box wow fadeInUp">
        <div>
          <span class="section-eyebrow">Contact</span>
          <h2>需要升级官网、系统或 AI 应用方案？</h2>
          <p>我们可以基于你的业务目标，快速给出更清晰的建设建议与实施路径。</p>
        </div>
        <router-link class="primary-btn" to="/contactus">立即咨询</router-link>
      </div>
    </section>
  </div>
</template>

<script>
import { WOW } from "wowjs";
import { serviceList, serviceStats } from "@/data/serviceData";

export default {
  name: "HomePage",
  data() {
    return {
      statsList: serviceStats,
      serviceList,
      valueList: [
        {
          title: "更贴近业务",
          content: "先理解业务目标与流程，再设计系统与页面，避免只做表面功能。"
        },
        {
          title: "交付更透明",
          content: "阶段目标清晰、过程可追踪，帮助企业更稳地推进项目落地。"
        },
        {
          title: "体验更现代",
          content: "兼顾视觉简洁度、响应式体验和内容表达，让品牌呈现更专业。"
        },
        {
          title: "后续可持续",
          content: "预留后期扩展能力，便于上线后的维护、迭代和新功能接入。"
        }
      ]
    };
  },
  mounted() {
    var wow = new WOW({
      boxClass: "wow",
      animateClass: "animated",
      offset: 0,
      mobile: true,
      live: true
    });
    wow.init();
  },
  methods: {
    serviceClick(id) {
      this.$router.push({
        name: "servicedetail",
        params: {
          id: id
        }
      });
    }
  }
};
</script>

<style scoped>
#HomePage {
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

.hero-section {
  padding: 64px 0 40px;
}

.hero-container {
  display: flex;
  align-items: stretch;
  gap: 32px;
}

.hero-copy,
.hero-panel {
  flex: 1;
}

.hero-copy {
  padding: 32px 0;
}

.hero-copy h1 {
  margin: 0 0 20px;
  color: #111827;
  font-size: 48px;
  line-height: 1.2;
  font-weight: 700;
}

.hero-copy p {
  max-width: 560px;
  color: #5b6475;
  font-size: 16px;
  line-height: 1.9;
}

.hero-actions {
  display: flex;
  gap: 16px;
  margin-top: 32px;
}

.primary-btn,
.ghost-btn {
  display: inline-block;
  padding: 14px 28px;
  border-radius: 999px;
  font-size: 14px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
}

.primary-btn {
  color: #fff;
  background: linear-gradient(135deg, #4f6bff, #7a5cff);
  box-shadow: 0 16px 30px rgba(79, 107, 255, 0.24);
}

.ghost-btn {
  color: #1f2937;
  background: rgba(255, 255, 255, 0.75);
  border: 1px solid rgba(17, 24, 39, 0.08);
}

.primary-btn:hover,
.ghost-btn:hover,
.text-link:hover {
  text-decoration: none;
  transform: translateY(-2px);
}

.hero-panel {
  padding: 12px;
  border-radius: 28px;
  background: linear-gradient(180deg, rgba(79, 107, 255, 0.08), rgba(122, 92, 255, 0.03));
}

.hero-card {
  background: rgba(255, 255, 255, 0.9);
  border: 1px solid rgba(79, 107, 255, 0.08);
  border-radius: 24px;
  box-shadow: 0 20px 45px rgba(15, 23, 42, 0.08);
}

.hero-card-primary {
  padding: 32px;
  margin-bottom: 20px;
}

.hero-card-primary h3 {
  margin: 0 0 12px;
  color: #111827;
  font-size: 28px;
}

.hero-card-primary p,
.hero-card-label {
  color: #5b6475;
}

.hero-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

.hero-stat {
  padding: 24px 18px;
  text-align: center;
}

.hero-stat strong {
  display: block;
  color: #111827;
  font-size: 28px;
}

.hero-stat span {
  color: #6b7280;
  font-size: 13px;
}

.company-section,
.value-section,
.service-section,
.cta-section {
  padding: 36px 0 80px;
}

.company-row {
  padding: 40px;
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 32px;
  box-shadow: 0 20px 45px rgba(15, 23, 42, 0.06);
}

.company-visual {
  padding: 20px;
  border-radius: 24px;
  background: linear-gradient(180deg, #f4f7ff, #eef3ff);
}

.company-row h2,
.section-heading h2,
.cta-box h2 {
  margin: 0 0 16px;
  color: #111827;
  font-size: 34px;
  line-height: 1.3;
}

.company-row p,
.section-heading p,
.cta-box p {
  color: #5b6475;
  font-size: 15px;
  line-height: 1.9;
}

.company-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-top: 28px;
}

.company-tags span {
  padding: 10px 16px;
  color: #3d4a63;
  background: #f3f6fb;
  border-radius: 999px;
  font-size: 13px;
}

.section-heading {
  max-width: 760px;
  margin: 0 auto 40px;
}

.value-card {
  height: 100%;
  padding: 28px;
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 24px;
  box-shadow: 0 18px 40px rgba(15, 23, 42, 0.05);
}

.value-index {
  display: inline-block;
  margin-bottom: 18px;
  color: #4f6bff;
  font-size: 24px;
  font-weight: 700;
}

.value-card h3,
.service-card h3 {
  margin: 0 0 12px;
  color: #111827;
  font-size: 22px;
}

.value-card p,
.service-card p {
  color: #5b6475;
  line-height: 1.8;
}

.service-heading {
  display: flex;
  align-items: end;
  justify-content: space-between;
  max-width: none;
}

.text-link {
  color: #4f6bff;
  font-weight: 600;
  text-decoration: none;
}

.service-card {
  display: flex;
  gap: 24px;
  height: 100%;
  margin-bottom: 24px;
  padding: 24px;
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 24px;
  box-shadow: 0 20px 42px rgba(15, 23, 42, 0.05);
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.service-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 26px 48px rgba(15, 23, 42, 0.08);
}

.service-card-copy {
  flex: 1;
}

.service-card-copy > span {
  display: inline-block;
  margin-bottom: 10px;
  color: #7c86a0;
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.service-card-copy ul {
  padding-left: 18px;
  margin: 18px 0 0;
  color: #475569;
}

.service-card-copy li {
  margin-bottom: 8px;
}

.service-card-image {
  width: 160px;
  min-width: 160px;
}

.service-card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 18px;
}

.cta-box {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  padding: 40px;
  background: linear-gradient(135deg, #111827, #1e293b);
  border-radius: 32px;
}

.cta-box h2,
.cta-box p {
  color: #fff;
}

.cta-box p {
  margin-bottom: 0;
  color: rgba(255, 255, 255, 0.76);
}

@media screen and (max-width: 997px) {
  .hero-container,
  .service-card,
  .cta-box,
  .service-heading {
    display: block;
  }

  .hero-copy h1 {
    font-size: 34px;
  }

  .hero-panel {
    margin-top: 24px;
  }

  .hero-grid {
    grid-template-columns: 1fr;
  }

  .company-row {
    padding: 24px;
  }

  .company-row h2,
  .section-heading h2,
  .cta-box h2 {
    font-size: 28px;
  }

  .service-card-image {
    width: 100%;
    min-width: auto;
    margin-top: 20px;
  }

  .cta-box .primary-btn {
    margin-top: 20px;
  }
}

@media screen and (max-width: 767px) {
  .hero-section,
  .company-section,
  .value-section,
  .service-section,
  .cta-section {
    padding: 24px 0 56px;
  }

  .hero-section {
    padding-top: 32px;
  }

  .hero-copy {
    padding: 8px 0;
  }

  .hero-copy h1 {
    font-size: 30px;
  }

  .hero-actions {
    flex-direction: column;
  }

  .primary-btn,
  .ghost-btn {
    width: 100%;
    text-align: center;
  }
}
</style>

