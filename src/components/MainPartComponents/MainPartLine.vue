<template>
    <div>
        <div class="circle"></div>
        <svg width="4" preserveAspectRatio="none" height="100%">
            <line x1="0" y1="0" x2="0" y2="50000" style="stroke:rgb(226, 230, 238);stroke-width:1" />
        </svg>
    </div>
</template>
<script>
</script>
<style scoped>
    .circle {
        position:relative;
        border: 1px solid rgb(226, 230, 238);
        padding: 5px;
        border-radius: 50%;
        filter: drop-shadow(0px 5px 50px #edd4d4);
        margin-top: 5px;
        width: 24px;
        height: 24px;
        background-color: white;
        margin-left: -11px
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
</style>