<template>
    <div class="userinfo" @click="bindViewTap">
        <img class="userinfo-avatar" v-if="userInfo.avatarUrl" :src="userInfo.avatarUrl" background-size="cover"/>
        <div class="userinfo-nickname">
            <card :text="userInfo.nickName"></card>
        </div>
    </div>
</template>

<script>
    import card from './card'
    export default{
        data(){
            return{
                userInfo: {}
            }
        },
        components: {
            card
        },
        methods:{
            getUserInfo () {
                // 调用登录接口
                wx.login({
                    success: () => {
                        wx.getUserInfo({
                            success: (res) => {
                                this.userInfo = res.userInfo
                            }
                        })
                    }
                })
            },
        },
        created () {
            // 调用应用实例的方法获取全局数据
            this.getUserInfo()
        }
    }
</script>

<style>
    body{
        background-color:#ff0000;
    }
</style>
