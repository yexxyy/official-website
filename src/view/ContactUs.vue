<template>
  <div id="ContactUs">
    <section class="contact-hero">
      <div class="container">
        <span class="section-eyebrow">Contact Us</span>
        <h1>欢迎沟通你的数字化项目需求</h1>
        <p>无论是官网升级、业务系统建设，还是 AI 应用落地，我们都可以一起评估可行路径。</p>
      </div>
    </section>

    <section class="contact-content">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <div class="map-card wow fadeInRight">
              <div id="map"></div>
            </div>
            <div class="contact-meta wow fadeInUp">
              <p><strong>电话：</strong>18200280142</p>
              <p><strong>地址：</strong>中国（四川）自由贸易试验区成都高新区交子北一路88号1栋2单元14层1413号</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import { WOW } from 'wowjs'
export default {
  name: "ContactUs",
  data() {
    return {};
  },
  mounted() {
    var BMap = window.BMap;
    if (!BMap) {
      var mapNode = document.getElementById("map");
      if (mapNode) {
        mapNode.innerHTML = '<div style="display:flex;align-items:center;justify-content:center;height:100%;color:#64748b;background:#f8fafc;border-radius:18px;">地图加载失败，请稍后重试</div>';
      }
      return;
    }
    var map = new BMap.Map("map"); // 创建地图实例
    var address = "中国（四川）自由贸易试验区成都高新区交子北一路88号1栋";
    var geocoder = new BMap.Geocoder();
    geocoder.getPoint(address, function(point) {
      if (point) {
        map.centerAndZoom(point, 18);
        map.enableScrollWheelZoom(true);
        var marker = new BMap.Marker(point);
        map.addOverlay(marker);
        var infoWindow = new BMap.InfoWindow(address, {
          width: 260,
          height: 50,
          title: "成都云从本图科技有限公司"
        });
        map.openInfoWindow(infoWindow, point);
      } else {
        var fallbackPoint = new BMap.Point(104.069545, 30.5907);
        map.centerAndZoom(fallbackPoint, 18);
        map.enableScrollWheelZoom(true);
        map.addOverlay(new BMap.Marker(fallbackPoint));
      }
    }, "成都市");
    var wow = new WOW();
    wow.init();
  }
};
</script>
<style scoped>
#ContactUs {
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

.contact-hero {
  padding: 72px 0 24px;
}

.contact-hero h1 {
  margin: 0 0 16px;
  color: #111827;
  font-size: 42px;
}

.contact-hero p,
.contact-form label,
.contact-meta p {
  color: #5b6475;
}

.contact-content {
  padding: 8px 0 80px;
}

.contact-form,
.map-card,
.contact-meta {
  background: #fff;
  border: 1px solid rgba(17, 24, 39, 0.06);
  border-radius: 24px;
  box-shadow: 0 18px 42px rgba(15, 23, 42, 0.05);
}

.map-card {
  padding: 12px;
}

#map {
  width: 100%;
  height: 560px;
  border-radius: 18px;
  overflow: hidden;
}

.contact-meta {
  margin-top: 16px;
  padding: 18px 20px;
}

.contact-meta strong {
  color: #111827;
}

@media screen and (max-width: 997px) {
  .contact-hero h1 {
    font-size: 32px;
  }

  .map-card,
  .contact-meta {
    margin-top: 20px;
  }
}

@media screen and (max-width: 767px) {
  .contact-hero {
    padding-top: 48px;
  }

  .contact-hero h1 {
    font-size: 28px;
  }

  .contact-content {
    padding-bottom: 56px;
  }

  #map {
    height: 420px;
  }
}
</style>

