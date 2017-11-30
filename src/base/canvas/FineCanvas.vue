/**
 * canvas绘图
 *
 * Created by Teller on 2017/11/29.
 */

 <template>
    <canvas
        :class="this.canvasCls"
        ref="canvas"
        :width="this.options.width"
        :height="this.options.height"
    />
 </template>

 <script>
function decorator(target, key, descriptor) {
    
}

export default {
    props: ['options'],
    mounted() {
        this.canvas = this.$ref.canvas;
        this.ctx = this.canvas.getContext('2d');
    },
    data: {
        
    },
    computed: {
        canvasCls() {
            return `bi-canvas ${this.options.cls}`;
        },
    },
    reset() {
        this.ctx.clearRect(0, 0, this.options.width, this.options.height);
    },
};
</script>
 
<style lang="less" scoped>
    .bi-canvas {
        width: 100%;
        height: 100%;
    }
</style>
 

