<template>
    <div>
        <div class="prism-player" id="J_prismPlayer"></div>
    </div>
</template>

<script>
    export default {
        name: 'AliPlayer',
        mounted: function () {
            // 初始化播放器
            var player = new Aliplayer({
                id: "J_prismPlayer", // 容器id
                // source: "http://cloud.video.taobao.com/play/u/2554695624/p/1/e/6/t/1/fv/102/28552077.mp4",  //视频地址,
                source: "http://devin-le.oss-cn-hangzhou.aliyuncs.com/lin.flv",
                cover: "http://cdn.img.mtedu.com/images/assignment/day_3.jpg",  //播放器封面图
                autoplay: false,      // 是否自动播放
                width: "100%",       // 播放器宽度
                height: "400px",      // 播放器高度
                playsinline: true,

            })
        },
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>