<template>
    <div class="event-add">
        <input type="text" class="n-input" v-model="content" placeholder="待办事项回车提交" @keyup.enter="submit">
    </div>
</template>

<script>
    export default {
        data () {
            return {
                content: ''
            }
        },
        methods: {
            submit () {
                let self = this,
                    params = {
                        id: 0,
                        type: 1,
                        content: '',
                        time: ''
                    };
                self.content = self.content.trim();
                if(self.content){
                    params.content = self.content;
                    self.$store.dispatch('addevent',params);
                    self.content = '';
                    self.$toast('添加成功');
                }
            }
        }
    }
</script>

<style lang="scss" rel="stylesheet/scss">
    .event-add{
        position: relative;
        padding:5px 0;
        font-size: 12px;
        .n-input{
            width:100%;
            height:40px;
            padding:7px 5px;
            line-height: 26px;
            border:1px solid #c0ccda;
            border-radius:2px;
            transition: border-color .2s cubic-bezier(.645,.045,.355,1);
            box-sizing: border-box;
            font-size:inherit;
            &:focus {
                outline: none;
            }
        }
        .add-btn{
            position: absolute;
            right:0;
            top:30px;
            width:80px;
            height:40px;
            line-height: 26px;
            color: #fff;
            /*transition: background .3s ease-in;*/
        }
    }
</style>
