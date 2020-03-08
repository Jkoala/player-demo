<template>
    <div class="video-content">
        <p>this is a flaPlayer demo this 播放器 有问题</p>
        <div class="flvplayer-app" id="videoElement"></div>
    </div>
</template>

<script>
    import FlvPlayer from 'flvplayer'

    export default {
        name: "flvPlayer",
        props: {
            src: {
                type: String,
                default: 'http://devin-le.oss-cn-hangzhou.aliyuncs.com/lin.flv'
            }
        },
        data() {
            return {
                flvPlayer: null
            }
        },
        mounted() {
            if (FlvPlayer.isSupported()) {
                var videoElement = document.getElementById('videoElement')
                var videoSrc = this.src
                this.flvPlayer = new FlvPlayer({
                    container: videoElement,
                    poster: 'https://devin-le.oss-cn-hangzhou.aliyuncs.com/2.jpg',
                    // url: videoSrc,
                    // decoder: './uncompiled/flvplayer-decoder-baseline.js',
                    // decoder: './a',
                    // decoder: FlvPlayer.,
                    loop: true,
                    autoPlay: false,
                    hasAudio: true,
                    control: true,
                    // muted: false,
                    volume: 0.7,
                    frameRate: 30,
                    maxTimeDiff: 200,
                    videoChunk: 1024 * 1024,
                    audioChunk: 64 * 1024,
                    width: 640,
                    height: 360,
                });

            }
        },
    }
</script>

<style scoped>
    .video-content {
        width: 400px;
        max-height: 400px;
    }
</style>