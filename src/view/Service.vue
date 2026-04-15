<template>
  <div id="Service">
    <section class="service-hero">
      <div class="container">
        <span class="section-eyebrow">Our Services</span>
        <h1>围绕企业数字化升级，提供更完整的服务方案</h1>
        <p>
          从品牌官网到业务系统，从技术团队支持到 AI 场景落地，我们帮助企业把想法更稳地变成可运行、可迭代的产品。
        </p>
      </div>
    </section>

    <section class="service-content">
      <div class="container">
        <div class="stats-row wow fadeInUp">
          <div class="stats-card" v-for="(item, index) in statsList" :key="index">
            <strong>{{ item.value }}</strong>
            <span>{{ item.label }}</span>
          </div>
        </div>

        <div class="service-list">
          <div class="service-item wow fadeInUp" v-for="(item, index) in serviceList" :key="index">
            <div class="service-item-image">
              <img :src="item.image" :alt="item.title">
            </div>
            <div class="service-item-content">
              <span>{{ item.engTitle }}</span>
              <h2>{{ item.title }}</h2>
              <p>{{ item.description }}</p>

              <div class="tag-row">
                <label>服务亮点</label>
                <div>
                  <em v-for="(point, pointIndex) in item.highlights" :key="pointIndex">{{ point }}</em>
                </div>
              </div>

              <div class="tag-row">
                <label>适用场景</label>
                <div>
                  <em v-for="(scene, sceneIndex) in item.scenarios" :key="sceneIndex">{{ scene }}</em>
                </div>
              </div>

              <div class="service-actions">
                <button class="detail-btn" @click="serviceClick(item.id)">查看详情</button>
                <span class="service-metric">{{ item.metric }}</span>
              </div>
            </div>
          </div>
        </div>

        <div class="process-box wow fadeInUp">
          <div class="process-heading">
            <span class="section-eyebrow">Delivery Process</span>
            <h2>服务协作流程更清晰</h2>
          </div>
          <div class="process-list">
            <div class="process-item" v-for="(item, index) in processList" :key="index">
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
import { WOW } from "wowjs";
import { serviceList, serviceStats } from "@/data/serviceData";

export default {
  name: "Service",
  data() {
    return {
      serviceList,
      statsList: serviceStats,
      processList: [
        {
          title: "需求沟通",
          content: "梳理目标、核心流程与预期成果，明确建设优先级。"
        },
        {
          title: "方案设计",
          content: "输出产品结构、视觉方向和技术实现思路，减少返工。"
        },
        {
          title: "开发交付",
          content: "按阶段推进开发、测试和上线，确保进度与质量可控。"
        },
        {
          title: "持续优化",
          content: "根据业务反馈继续迭代，提升长期使用价值。"
        }
      ]
    };
  },
  mounted() {
    var wow = new WOW();
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
#Service {
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

.service-hero {
  padding: 72px 0 32px;
}

.service-hero h1 {
  max-width: 760px;
  margin: 0 0 18px;
  color: #111827;
  font-size: 42px;
  line-height: 1.25;
}

.service-hero p {
  max-width: 760px;
  color: #5b6475;
  font-size: 16px;
  line-height: 1.9;
}

.service-content {
  padding: 8px 0 80px;
}

.stats-row {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin-bottom: 28px;
}

.stats-card,
.service-item,
.process-box {
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 28px;
  box-shadow: 0 18px 42px rgba(15, 23, 42, 0.05);
}

.stats-card {
  padding: 28px;
  text-align: center;
}

.stats-card strong {
  display: block;
  color: #111827;
  font-size: 30px;
}

.stats-card span {
  color: #6b7280;
}

.service-list {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.service-item {
  display: flex;
  gap: 28px;
  padding: 24px;
}

.service-item-image {
  width: 280px;
  min-width: 280px;
}

.service-item-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 22px;
}

.service-item-content {
  flex: 1;
}

.service-item-content > span {
  display: inline-block;
  margin-bottom: 12px;
  color: #7c86a0;
  font-size: 12px;
  letter-spacing: 1px;
  text-transform: uppercase;
}

.service-item-content h2,
.process-heading h2 {
  margin: 0 0 14px;
  color: #111827;
  font-size: 30px;
}

.service-item-content p,
.process-item p {
  color: #5b6475;
  line-height: 1.85;
}

.tag-row {
  margin-top: 20px;
}

.tag-row label {
  display: block;
  margin-bottom: 10px;
  color: #111827;
  font-size: 14px;
}

.tag-row em {
  display: inline-block;
  margin: 0 10px 10px 0;
  padding: 10px 14px;
  color: #44506a;
  font-style: normal;
  background: #f4f7fb;
  border-radius: 999px;
}

.service-actions {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-top: 28px;
}

.detail-btn {
  padding: 12px 24px;
  color: #fff;
  background: linear-gradient(135deg, #4f6bff, #7a5cff);
  border: none;
  border-radius: 999px;
  outline: none;
}

.service-metric {
  color: #4f6bff;
  font-weight: 600;
}

.process-box {
  margin-top: 32px;
  padding: 32px;
}

.process-list {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
}

.process-item {
  padding: 24px 0 0;
}

.process-item strong {
  color: #4f6bff;
  font-size: 28px;
}

.process-item h3 {
  margin: 12px 0;
  color: #111827;
  font-size: 20px;
}

@media screen and (max-width: 997px) {
  .service-hero h1 {
    font-size: 34px;
  }

  .stats-row,
  .process-list {
    grid-template-columns: 1fr;
  }

  .service-item {
    display: block;
  }

  .service-item-image {
    width: 100%;
    min-width: auto;
    margin-bottom: 20px;
  }
}

@media screen and (max-width: 767px) {
  .service-hero {
    padding: 64px 0 20px;
  }

  .service-content {
    padding-bottom: 56px;
  }

  .service-hero h1,
  .service-item-content h2,
  .process-heading h2 {
    font-size: 28px;
  }

  .process-box {
    padding: 24px;
  }

  .service-actions {
    display: block;
  }

  .service-metric {
    display: block;
    margin-top: 12px;
  }
}
</style>

