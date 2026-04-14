<template>
  <div id="ServiceDetail">
    <section class="detail-hero">
      <div class="container">
        <span class="section-eyebrow">Service Details</span>
        <h1>更具体的服务说明与交付内容</h1>
        <p>按业务场景查看服务能力、交付成果与适用方向，帮助你更快判断合作方式。</p>
      </div>
    </section>

    <section class="detail-content">
      <div class="container detail-layout">
        <aside class="detail-nav">
          <div class="nav-card">
            <p>服务目录</p>
            <a
              v-for="(item, index) in serviceList"
              :key="index"
              :href="'#' + item.id"
              :class="{ active: item.id === currentId }"
              @click="currentId = item.id"
            >
              {{ item.title }}
            </a>
          </div>
        </aside>

        <div class="detail-main">
          <section class="detail-block wow fadeInUp" v-for="(item, index) in serviceList" :key="index" :id="item.id">
            <div class="detail-block-header">
              <div>
                <span>{{ item.engTitle }}</span>
                <h2>{{ item.title }}</h2>
              </div>
              <em>{{ item.metric }}</em>
            </div>
            <p class="detail-summary">{{ item.description }}</p>

            <div class="detail-grid">
              <div class="detail-card">
                <h3>服务亮点</h3>
                <ul>
                  <li v-for="(point, pointIndex) in item.highlights" :key="pointIndex">{{ point }}</li>
                </ul>
              </div>
              <div class="detail-card">
                <h3>交付内容</h3>
                <ul>
                  <li v-for="(deliverable, deliverableIndex) in item.deliverables" :key="deliverableIndex">{{ deliverable }}</li>
                </ul>
              </div>
              <div class="detail-card">
                <h3>适用场景</h3>
                <ul>
                  <li v-for="(scene, sceneIndex) in item.scenarios" :key="sceneIndex">{{ scene }}</li>
                </ul>
              </div>
            </div>
          </section>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import { WOW } from "wowjs";
import { serviceList } from "@/data/serviceData";

export default {
  name: "ServiceDetail",
  data() {
    return {
      currentId: "section-1",
      serviceList
    };
  },
  mounted() {
    this.currentId = this.$route.params.id || "section-1";
    this.$nextTick(function() {
      var target = document.getElementById(this.currentId);
      if (target) {
        var top = target.getBoundingClientRect().top + window.pageYOffset - 120;
        window.scrollTo(0, top);
      }
    });
    var wow = new WOW();
    wow.init();
  }
};
</script>

<style scoped>
#ServiceDetail {
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

.detail-hero {
  padding: 72px 0 24px;
}

.detail-hero h1 {
  margin: 0 0 16px;
  color: #111827;
  font-size: 42px;
}

.detail-hero p,
.detail-summary,
.detail-card li {
  color: #5b6475;
  line-height: 1.9;
}

.detail-content {
  padding: 8px 0 80px;
}

.detail-layout {
  display: flex;
  align-items: flex-start;
  gap: 28px;
}

.detail-nav {
  width: 240px;
  min-width: 240px;
  position: sticky;
  top: 32px;
}

.nav-card,
.detail-block {
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 28px;
  box-shadow: 0 18px 42px rgba(15, 23, 42, 0.05);
}

.nav-card {
  padding: 22px;
}

.nav-card p {
  margin-bottom: 12px;
  color: #111827;
  font-size: 16px;
  font-weight: 700;
}

.nav-card a {
  display: block;
  padding: 12px 14px;
  color: #52607a;
  text-decoration: none;
  border-radius: 14px;
}

.nav-card a.active,
.nav-card a:hover {
  color: #4f6bff;
  background: #f3f6ff;
  text-decoration: none;
}

.detail-main {
  flex: 1;
}

.detail-block {
  margin-bottom: 24px;
  padding: 28px;
}

.detail-block-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 18px;
}

.detail-block-header span {
  display: inline-block;
  margin-bottom: 8px;
  color: #7c86a0;
  font-size: 12px;
  letter-spacing: 1px;
  text-transform: uppercase;
}

.detail-block-header h2 {
  margin: 0;
  color: #111827;
  font-size: 30px;
}

.detail-block-header em {
  padding: 10px 16px;
  color: #4f6bff;
  font-style: normal;
  font-weight: 600;
  background: #f3f6ff;
  border-radius: 999px;
}

.detail-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 18px;
  margin-top: 24px;
}

.detail-card {
  padding: 24px;
  background: #f8fafc;
  border-radius: 22px;
}

.detail-card h3 {
  margin: 0 0 14px;
  color: #111827;
  font-size: 20px;
}

.detail-card ul {
  padding-left: 18px;
  margin: 0;
}

.detail-card li {
  margin-bottom: 10px;
}

@media screen and (max-width: 997px) {
  .detail-layout {
    display: block;
  }

  .detail-nav {
    width: auto;
    min-width: auto;
    margin-bottom: 24px;
    position: static;
  }

  .detail-grid {
    grid-template-columns: 1fr;
  }
}

@media screen and (max-width: 767px) {
  .detail-hero {
    padding-top: 48px;
  }

  .detail-hero h1,
  .detail-block-header h2 {
    font-size: 28px;
  }

  .detail-block-header {
    display: block;
  }

  .detail-block-header em {
    display: inline-block;
    margin-top: 16px;
  }
}
</style>
