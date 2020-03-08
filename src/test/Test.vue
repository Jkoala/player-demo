<template>
    <div id="video-content">
        <!--        <flvPlayer></flvPlayer>-->
        <!--        <RtmpLive></RtmpLive>-->
        <AliPlayer></AliPlayer>
    </div>
</template>

<script>
    import AliPlayer from "../components/AliPlayer";

    export default {
        name: "Test",
        components: {
            AliPlayer,
        }
    }
</script>

<style scoped>
    #video-content {
        width: 600px;
        height: 600px;
    }
</style>