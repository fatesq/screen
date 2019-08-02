<template>
  <div id="app">
    <h1 class="title">
      <img src="./assets/lineLeft.png">
      <div class="center"><img src="./assets/icon.png" style="padding-right: 30px"><span style="color: #E6F0FF">标题</span></div>
      <img src="./assets/lineRight.png">
    </h1>
    <div class="title-l">
      <img src="./assets/line.png">
    </div>
    <div class="page">
      <div class="left">
        <div>
          <Title :title="'司法网拍'" />
          <div class="box">
            <NestedPies />
          </div>
        </div>
        <div>
          <Title :title="'失信人统计'"/>
          <div class="box">
            <LineBar />
            <CustPie />
          </div>
        </div>
      </div>
      <div class="middle">
        <div class="info">
          <div>收案数 <span>856件</span></div>
          <div>结案数 <span>856件</span></div>
          <div>未结数 <span>856件</span></div>
        </div>
        <img src="./assets/map.png" style="margin: -70px 0px -70px" />
        <div>
          <div style="display: flex; height: 208px">
            <Gauge1 />
            <Gauge2 />
            <Gauge3 />
          </div>
        </div>
        <div>
          <Title :title="'核心指标'" />
          <div class="box">
            <LineRow />
          </div>
        </div>
      </div>
      <div class="right">
        <div>
          <Title :title="'执法案件告警'"/>
          <div class="box">
           
          </div>
        </div>
        <div>
          <Title :title="'套路贷告警'"/>
          <div class="box">
            <LineBar2 />
          </div>
        </div>
        <div>
          <Title :title="'办案进度'"/>
          <div class="box">
            <LineRow2 />
          </div>
        </div>        
      </div>
    </div>
  </div>
</template>
<script>
import NestedPies from './components/NestedPies';
import LineBar from './components/LineBar';
import LineBar2 from './components/LineBar2';
import CustPie from './components/CustPie';
import Gauge1 from './components/Gauge1';
import Gauge2 from './components/Gauge2';
import Gauge3 from './components/Gauge3';
import LineRow from './components/LineRow';
import LineRow2 from './components/LineRow2';
import Title from './components/Title';

export default {
  name: 'index',
  components: {
    NestedPies,
    LineBar,
    CustPie,
    Gauge1,
    Gauge2,
    Gauge3,
    LineRow,
    LineBar2,
    LineRow2,
    Title
  }
}
</script>

<style lang="less">
html, body {
  padding: 0;
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: radial-gradient(rgb(22,20,136)  -24%, rgb(12,8,95) 100%);
}
.info {
  display: flex;
  justify-content: space-around;
  align-items: center;
  div {
    padding: 5px;
    font-size: 26px;
    color: #FFF;
    span {
      font-size: 36px;
      color: yellow;
      text-decoration: underline;
    }
  }
}
.page {
  display: flex;
  justify-content: space-around;
  .left {
    flex: 1 1 30%;
    padding: 10px 15px 10px 30px;
  }
  .middle {
    flex: 1 1 40%;
    padding: 10px 15px;
  }
  .right {
    flex: 1 1 30%;
    padding: 10px 30px 10px 15px;
  }
}
.title {
  display: flex;
  justify-content: center;
  align-items: center;
  .center {
    padding: 0px 40px;
    display: flex;
    align-items: center;
    font-size: 46px;
  }
}
.title-l {
  display: flex;
  justify-content: center;
  img {
    margin-top: -50px;
    width: 50%;
  }
}
.box {
  border: 2px solid #0B42F5;
}
</style>
