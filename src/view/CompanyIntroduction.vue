<template>
    <div id="CompanyIntroduction">
        <div class="banner container-fuild text-center">关于我们</div>
        <div class="container">
            <div class="row CompanyIntroduction-container">
                <div class="col-xs-12 col-sm-12 col-md-6 wow zoomIn">
                    <img class="img-responsive center-block" src="@/assets/img/about_img.png">
                </div>
                <div class="col-xs-12 col-sm-12 col-md-6">
                    <h3>成都云从本图科技有限公司</h3>
                    <p class=".text-justify">是一家以科技创意为核心的技术服务公司, 聚集了众多对软件开发和界面设计有独特创意的高端人才, 致力于为企业提供软件开发, 网站建设, 网页设计, IT外包, 手机应用开发, 互联网营销, 微信平台开发等解决方案。</p>
                    <p class=".text-justify">在过去的服务案例中，我们成功帮助众多企业通过数字化、AI和定制开发软件，降低运营成本，提升市场表现。未来，云从本图将继续秉承专业、创新、务实的服务理念，不断提升自身的服务水平和能力，为更多的企业提供优质、高效的服务，助力企业实现数字化的可持续发展。</p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import { WOW } from 'wowjs';
export default {
    name: 'CompanyIntroduction',
    data(){
        return{

        }
    },
    mounted(){
        var wow = new WOW();
        wow.init();
    }
}
</script>
<style scoped>
.banner{
    color: #fff;
    font-size: 30px;
    height: 150px;
    line-height: 150px;
    background-image: url('../assets/img/banner1.png');
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment: scroll;
    background-position: center center;
}
.row{
    margin-right: 0;
    margin-left: 0;
}
.CompanyIntroduction-container{
    padding: 100px 0;
    color: #808080;
    transition: all ease 0.5s;
}
.CompanyIntroduction-container>div>p{
    font-size: 14px;
    line-height: 2.5rem;
}
@media screen and (max-width: 997px){
    .CompanyIntroduction-container{
    padding: 10px 0;
    color: #808080;
}
}
</style>

