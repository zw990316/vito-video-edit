<template>
    <div ref="canvasContainerRef" class="canvas-container">
        <canvas id="canvasTimeLine" ref="trackTimeLineRef"  v-bind="canvasAttr" ></canvas>
    </div>
</template>
<script setup>
import { formatTime } from '../../utils/common';
import { ref ,reactive,computed, onMounted,nextTick} from 'vue'

console.log(formatTime(100000));

const canvasContainerRef = ref()
const trackTimeLineRef = ref()
const canvasAttr = reactive({
    width:0,
    height:0
})

// const canvasStyle = computed(()=>{
//     return {
//         width:`${canvasAttr.width}px`,
//         height:`${canvasAttr.height}px`,
//     }
// })

onMounted(() => {
    nextTick(()=>{
        drawTrackTimeLine()
    })
})

const drawTrackTimeLine = function(){
    const ctx = trackTimeLineRef.value.getContext('2d')
    console.log(ctx)
    const { width, height } = canvasContainerRef.value.getBoundingClientRect()
    console.log(width);
    const littleCell = 15
    const largeCell = 150
    const start = 0
    const largeCellOffsetX = largeCell - start
    const littleCellOffsetX = littleCell - start
    canvasAttr.width = width
    canvasAttr.height = height
    nextTick(()=>{
        ctx.strokeStyle = 'white'
        ctx.fillStyle = 'white';
        ctx.font="10px Verdana";
        ctx.lineWidth = 1
        ctx.scale(1, 1);
        ctx.clearRect(0, 0, width, height);

        ctx.beginPath();
        for(let i= 0,times=1;i< width;i += largeCell,times++){
            let x = largeCellOffsetX + ctx.lineWidth + i
            ctx.moveTo(x,0)
            ctx.save()
            const text = getLargeTimeText(times)
            ctx.fillText(text, x+5, 20);
            ctx.restore()
            ctx.lineTo(x,height * 0.5);
        }
        ctx.stroke()
        ctx.closePath()

        ctx.beginPath();

        for(let i= 0;i< width;i++){
            const x = littleCellOffsetX + ctx.lineWidth + littleCell * i
            if(i % 10 !== 9){
                ctx.moveTo(x,0)
                ctx.lineTo(x,height*0.2);
            }

        }
        ctx.stroke()
        ctx.closePath()
    })

}

const getLargeTimeText = function(times){
    let time = times * 10 //一格10s
    console.log(formatTime(time * 1000).str);
    return formatTime(time * 1000).str
}

window.addEventListener('resize', drawTrackTimeLine, false);
</script>
<style lang="scss" scoped>
.canvas-container{
    height: 30px;
}

</style>