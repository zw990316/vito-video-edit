<template>
    <div class="canvas-content">
        <canvas ref="canvasPlayerRef" id="canvasPlayer" width="780" height="439"></canvas>
    </div>
    <el-button @click="paint">生成视频</el-button>
</template>
<script setup>
import { createFFmpeg ,fetchFile} from '@ffmpeg/ffmpeg'
import { ref,onMounted } from 'vue'
const videoUrl = ref('')
const canvasPlayerRef = ref()

// const ffmpeg = createFFmpeg({
//     corePath: '/ffmpeg/ffmpeg-core.js',
//     logger:({ message }) => console.log("message",message),
//     log:true
// })

// function drawImage(video){
//     const ctx = canvasPlayerRef.value.getContext('2d')
//     ctx.drawImage(video,10,10)
// }

const paint = async function(){
    const ffmpeg = createFFmpeg({
        corePath: '/ffmpeg/ffmpeg-core.js',
        // logger:({ message }) => console.log("message",message),
        // log:true
    })
    if (!crossOriginIsolated) {
        alert('当前环境不可用')
        return
    }
    if(!ffmpeg.isLoaded()){
        await ffmpeg.load()
    }
    // ffmpeg.FS('mkdir', '/frame');
    // const dir= ffmpeg.FS('readdir', '/frame')
    // console.log("dir",dir.indexOf('frame')> -1);
    // const video = await fetchFile('/test-video.mp4')
    // ffmpeg.FS('writeFile','test-video.mp4',video)
    // try {
        await ffmpeg.run([])
        // await ffmpeg.value.run(['-i', 'test-video.mp4','-vf' ,'fps=30', '/frame/pic-%d.jpg'])
    // } catch (error) {
    //     console.log(error);
    // }
    
    // const data = ffmpeg.FS('readFile', await fetchFile(`/frame/test.mp4`));
    // console.log("datadatadata",data.buffer);
    // const blob = new Blob([data.buffer], { type: 'jpg' })
    // const ctx = canvasPlayerRef.value.getContext('2d')
    // ctx.drawImage(blob,10,10)
    // const file = await fetchFile('/test-video.mp4')
    // const blob = getVideoBlob(buffer)
    // drawImage(blob)
}


const getVideoBuffer =  async function(){

    if (!crossOriginIsolated) {
        alert('当前环境不可用')
        return
    }
    if(!ffmpeg.value.isLoaded()){
        await ffmpeg.value.load()
    }
    // const video = await fetchFile('/test-video.mp4')
    // console.log("video",video);
    // ffmpeg.value.FS('writeFile','test-video.mp4',video)
    await ffmpeg.value.run(['-i', '/test-video.mp4', '-vf', `fps=30`, '-s', `1280*720`, `/frame/pic-%d.jpg`])

    // console.log(aa.then(console.log(res)));
    // const data = ffmpeg.value.FS('readFile','test-video.mp4')
    // return data.buffer
}

const mkdir = async function(paths) {
        paths.forEach(filePath => {
            ffmpeg.value.FS('mkdir', filePath);
        });
    }
// const getVideoBlob = function(buffer){
//     return new Blob([buffer], { type: 'video/mpeg4' })
// }
// const getVideoUrl = function (buffer){
//     const vidioBlob = getVideoBlob(buffer)
//     return URL.createObjectURL(vidioBlob)
// }

// onMounted(() => {
//     paint()
// })
</script>
<style lang="scss">
.canvas-content{
    display: flex;
    width: 100%;
    justify-content: center;
    align-items: center;
    #canvas{
        // width:780px;
        // height: 439px;
        background-color: #000000;
    }
}
</style>