
<template>
  <div class="layout">
    <Menu mode="horizontal" theme="dark" active-key="1">
      <div class="layout-logo"></div>
      <div class="layout-nav">
        <Menu-item name="menu1">
          <Icon type="ios-navigate"></Icon>
          首页
        </Menu-item>
        <Menu-item name="menu2">
          <Icon type="ios-keypad"></Icon>
          媒体
        </Menu-item>
        <Menu-item name="menu3">
          <Icon type="ios-analytics"></Icon>
          电影
        </Menu-item>
        <Menu-item name="menu4">
          <Icon type="ios-paper"></Icon>
          直播
        </Menu-item>
      </div>
    </Menu>
    <div class="layout-breadcrumb">
      <Breadcrumb>
        <Breadcrumb-item href="#">首页</Breadcrumb-item>
        <Breadcrumb-item href="#">应用中心</Breadcrumb-item>
        <Breadcrumb-item>APP</Breadcrumb-item>
      </Breadcrumb>
    </div>
    <div class="layout-content">
      <Row class="video-row">
        <i-col span="3">
          <RtmpLive :src="items[2].videoSrc"></RtmpLive>
        </i-col>
        <i-col span="3">
          <flv :src="items[5].videoSrc"></flv>
        </i-col>
        <i-col span="3">
          <VuePlayer></VuePlayer>
        </i-col>
        <i-col span="3">
          <AliPlayer></AliPlayer>
        </i-col>
      </Row>
    </div>
    <div class="layout-copy">
      2020 & copy devin
    </div>
  </div>
</template>
<script>
  import flv from '../components/flv'
  import RtmpLive from "../components/RtmpLive";
  import VuePlayer from "../components/VuePlayer";
  import AliPlayer from "../components/AliPlayer";

  export default {
    name: 'Main',
    components: {
      AliPlayer,
      VuePlayer,
      RtmpLive,
      flv
    },
    data() {
      return {
        descript: "vue-player 实验",
        items: [
          {title: '香港卫视', videoSrc: 'rtmp://live.hkstv.hk.lxdns.com/live/hks1'}, //0
          {title: '香港财经', videoSrc: 'rtmp://202.69.69.180:443/webcast/bshdlive-pc'},  // 1
          {title: '湖南卫视', videoSrc: 'rtmp://58.200.131.2:1935/livetv/hunantv'},  // 2
          {title: '美国中文电视', videoSrc: 'rtmp://media3.sinovision.net:1935/live/livestream'},  // 3
          {title: '我的阿里云服务器mp4', videoSrc: "http://devin-le.oss-cn-hangzhou.aliyuncs.com/1.mp4"}, // 4
          {title: '阿里云服务器flv', videoSrc: 'http://devin-le.oss-cn-hangzhou.aliyuncs.com/lin.flv'},  //5
          {title: 'MP4成功测试', videoSrc: 'http://vjs.zencdn.net/v/oceans.mp4'}  //6
        ]
      }
    }
  }
</script>

<style scoped lang="less">
  .layout {
    border: 1px solid #d7dde4;
    background: #f5f7f9;
  }

  .layout-logo {
    width: 100px;
    height: 30px;
    background: #5b6270;
    border-radius: 3px;
    float: left;
    position: relative;
    top: 15px;
    left: 20px;
  }

  .layout-nav {
    width: 420px;
    margin: 0 auto;
  }

  .layout-breadcrumb {
    padding: 10px 15px 0;
  }

  .layout-content {
    min-height: 500px;
    margin: 15px;
    overflow: hidden;
    background: #fff;
    border-radius: 4px;
    height: 700px;
  }

  .layout-copy {

    text-align: center;
    padding: 10px 0 20px;
    color: #9ea7b4;
    position: relative;
    bottom: 0px;
    height: 60px;
  }

  .video-row .ivu-col {
    height: 300px;
    width: 400px;
    /*display: block;*/
    background-color: #b4ff5b;
    margin: 30px;
  }
</style>