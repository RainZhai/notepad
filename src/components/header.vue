<template>
    <header class="">
        <h1>工作事项 <a class="t-btn" @click="showTools"><span></span></a></h1>
    </header>
</template>
<script>
    export default {
        methods: {
            showTools(){
                this.$emit('tools');
            }
        }
    }
</script>

<style lang="scss" rel="stylesheet/scss">
    header{
    	position:relative;
        width:100%;
        height:45px;
        z-index:100;
        h1{
            position: relative;
            width:100%;
            max-width:800px;
            margin:0 auto;
            line-height: 45px;
            text-align: center;
            color: #fff;
            font-size: 14px;
            a.t-btn{
                position: absolute;
                left:10px;
                top:11px;
                width:20px;
                height:24px;
                cursor: pointer;
            }
            span,span:before,span:after{
                position: absolute;
                left:0;
                width:20px;
                height:4px;
                content: '';
                background: #fff;
            }
            span{
                top:11px;
                &:before{
                    top:0;
                    transform: translateY(-7px);
                    transition: all .3s;
                }
                &:after{
                    transform: translateY(7px);
                    transition: all .3s;
                }
            }
        }
    }
</style>
