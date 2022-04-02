
<template>
    <kinesis-container class="header">
    <!-- 圆圈 start -->
      <kinesis-element v-for="item in circleDataList" :key="item" :class="`circle circle-${item}`" 
      :strength="40" type='translate' axis="x" transformOrigin='center' tag='div'>
      </kinesis-element>
      <!-- 圆圈 end -->

      <!-- 大标题 start -->
        <h1>
          <kinesis-element class="title" :type="item.type" v-for="(item, index) in titleList" 
          :key="index" :strength="20" tag="span" :style="`margin-top:${setMarginTopValue(index,titleList)}`">
          {{item.key}}
          </kinesis-element>
        </h1>
        <!-- 大标题 end -->

        <!-- 副标题 start -->
        <kinesis-element class="catcher" :originY="10" type="depth" transformOrigin='center 200px' tag="div"> 普诺得新能源 </kinesis-element>
        <kinesis-element class="catcher" :originY="20" type="depth" transformOrigin='center 200px' tag="div"> 专业的充电设备 </kinesis-element>
        <kinesis-element class="catcher" :originY="30" type="depth" transformOrigin='center 200px' tag="div"> 让汽车充电更安全 </kinesis-element>
        <!-- 副标题 end -->

        <!-- 可点击icon start -->
        <kinesis-element class="catcher github"  type="depth" transformOrigin='center 200px' tag="div"> 
          <a href="https://github.com/Aminerman/vue-kinesis" target="_blank">
          <img src="https://aminerman.com/kinesis/img/github.0c83fd0d.svg" height="30" alt=""></a>
        </kinesis-element>
        <!-- 可点击icon end -->
    </kinesis-container>

    <div class="intro">
        <div class="container">
            <h2 class="center">关于我们 / ABOUT US </h2>
            <p class="code"> 
              <span class="vue">南京瑞凡达新能源科技有限公司</span>，致力于研发及生产汽车专用产品，公司自2013年起从事新能源汽车充电设备的研究与生产，产品通过TS16949、CE、TUV等认证，已获得多项发明专利。 <br/> 
              <span>公司主要产品：</span>包括国标、欧标、美标新能源汽车便携式充电枪、桩用双头充电枪、新能源汽车交流充电桩、智能免接地插座等。<br/>
              <span>产品应用领域：</span>多种新能源汽车充电场景，如便携式交流充电、停车场写字楼运营版交流充电、旅途中临时充电等。<br/>
              <span>保养和维护：</span>公司设立专业服务部门，您购买的产品如有任何质量问题，请联系购买店铺的商家客服，我们将尽快为您安排解决。
              </p>

          </div>
      </div>
</template>
<script>
export default {
setup() {
let circleDataList = ["blue","purple","yellow","green","orange","red"];
// let titleList = ['k','i','n','e','s','i','s'];
let titleList = [{key:'k',type:'rotate'},{key:'i',type:'translate'} , {key:'n',type:'rotate'}, {key:'e',type:'translate'}, {key:'s',type:'translate'}, {key:'i',type:'rotate'}, {key:'s',type:'translate'}];

let topAry = ['-20px','-7px' , '8px', '13px', '-5px', '0px'];
 const setMarginTopValue = (index,titleList)=>{
   let ind=index
    if(index===0 || index===titleList?.length-1){
      return '0px';
    }else {
      return topAry[titleList?.length%ind];
    }
  }
   return {
      setMarginTopValue,
      circleDataList,
      titleList
    }
 } 
}
</script>


<style scoped>
  .header{
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-orient: vertical;
      -webkit-box-direction: normal;
      -ms-flex-direction: column;
      flex-direction: column;
      -webkit-box-pack: center;
      -ms-flex-pack: center;
      justify-content: center;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
      height: 90vh;
      position: relative;
  }
  .circle.circle-blue {
      background-color: #eaf1fa;
      width: 32vw;
      height: 32vw;
      top: 5%;
      right: -16vw;
  }
  .circle.circle-purple {
      border: 25px solid #f2eafa;
      width: 16vw;
      height: 16vw;
      left: 50%;
  }
  .circle.circle-yellow {
      background-color: #faf9ea;
      width: 8vw;
      height: 8vw;
      left: 30%;
      top: 25%;
  }
  .circle.circle-green {
      background-color: #eafaf2;
      width: 10vw;
      height: 10vw;
      right: 20%;
      top: 90%;
  }
  .circle.circle-orange{
      border: 25px solid #faf3ea;
      width: 8vw;
      height: 8vw;
      left: 20%;
      top: 60%;
  }
  .circle.circle-red {
      background-color: #faeaea;
      width: 12vw;
      height: 12vw;
      left: -4.8vw;
      top: 25%;
  }
  .circle {
      border-radius: 100%;
      position: absolute;
  }

  .header h1 {
    position: relative;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    color: #351b1b;
    font-size: 72px;
  }

  .header .catcher {
    position: relative;
    z-index: 5;
  }
   .header .github {
    margin-top: 20px;
  }

  .intro {
    margin-top: 130px;
  }
  .container {
    width: 800px;
    max-width: 90%;
    margin: 0 auto;
  }
  .center {
    text-align: center;
  }
  h2 {
    font-size: 25px;
    margin-top: 30px;
  }
  .code {
    background-color: #eaf1fa;
    padding: 10px 20px;
    border-radius: 10px;
    margin: 0 auto;
    margin-top: 30px;
    max-width: 600px;
    line-height: 1.5;
  }
  .vue {
    color: #19ad9b;
  }
  .container span {
    font-weight: 700;
  }
</style>
