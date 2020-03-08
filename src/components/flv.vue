<template>
  <div class="video-content">
    <video id="videoElement" class="flvplayer-app">

    </video>
    <!--    <video-player class="vjs-custom-skin flvplayer-app" id="videoElement"> </video-player>-->
    <!--    <VideoPlayer id="videoElement"  class="flvplayer-app"> </VideoPlayer>-->
  </div>

</template>

<script>

  // import flvPlayer  from 'flvplayer'
  import flvPlayer from 'flv.js'

  export default {
    name: 'flv',
    data() {
      return {
        flvPlayer: null,
      }
    },
    props: {
      src: {
        type: String,
        default: 'http://devin-le.oss-cn-hangzhou.aliyuncs.com/lin.flv'
      }
    },
    mounted() {
      if (flvPlayer.isSupported()) {
        var videoElement = document.getElementById('videoElement')
        var videoSrc = this.src
        this.flvPlayer = flvPlayer.createPlayer({
          // url:"http://cyberplayerplay.kaywang.cn/cyberplayer/demo201711-L1.flv",
          url: videoSrc,
          type: 'flv',

        })
        this.flvPlayer.attachMediaElement(videoElement)
        this.flvPlayer.load()
        this.flvPlayer.play()

      }
    },
    computed: {
      player() {
        return this.$refs.videoPlayer.player
      }
    },
    methods: {
      play() {
        this.flvPlayer.play();
      },
      pause() {
        this.flvPlayer.pause();
      }
    }
  }
</script>

<style lang="less" scoped>
  .flvplayer-app {
    width: 400px;
    max-height: 400px;
    align-self: flex-start;
  }

  .video-content {
    align-self: flex-start;
  }
</style>
