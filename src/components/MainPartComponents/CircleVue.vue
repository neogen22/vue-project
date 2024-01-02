<template>
    <div class="wrapper" ref="wrapperDivLength">
        <div class="circle"></div>
        <svg :height="wrapperLength" class="line" width="1px">
            <line x1="0" y1="0" x2="0" :y2="wrapperLength" style="stroke:rgb(226 230 238);stroke-width:1"/>
        </svg>        
    </div>    
</template>

<script>
    export default {
        data() {
            return {
                wrapperLength: 0,                
            }
        },
        methods: {
            changeLine() {
                if (this.wrapperLength !== this.$refs.wrapperDivLength.clientHeight) {
                    this.wrapperLength = this.$refs.wrapperDivLength.clientHeight
                }
            }
        },
        mounted() {
            this.$nextTick(() => {               
                    this.wrapperLength = this.$refs.wrapperDivLength.clientHeight;
            })
            setInterval(() => {
                this.changeLine()
            }, 250)
        },
}
</script>

<style scoped>
    .line {
        position: absolute;
        margin-top: 28px;
        margin-left: 12px;
        padding: 0; 
    }
    .circle {
        position:relative;
        border: 1px solid rgb(226, 230, 238);
        padding: 5px;
        border-radius: 50%;
        filter: drop-shadow(0px 5px 50px #edd4d4);
        margin-top: 5px;
        width: 24px;
        height: 24px;
        background-color: white
    }
    .circle::before {
        display: block;
        content: ' ';
        background-color: rgba(85, 49, 167);
        width: 6px;
        height: 6px;
        border-radius: 50%;
        margin-top: 3px;
        margin-left: 3px;
    }
    .wrapper {
        display:flex; 
        flex-direction: column;        
    }
</style>