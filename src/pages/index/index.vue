<template>
    <div class="container" @click="clickHandle('test click', $event)">

        <user></user>

        <div class="welcome">欢迎使用~</div>

        <a class="usermotto" href="../logo/main">
            <div class="user-motto">
                <card :text="motto"></card>
            </div>
        </a>

        <a class="description" href="../description/main">使用说明</a>
    </div>
</template>

<script>
import card from '@/components/card'
import user from '@/components/user'

export default {
  data () {
    return {
      motto: '开始使用'
    }
  },

  components: {
    card,
    user
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      wx.navigateTo({ url })
    },
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
    clickHandle (msg, ev) {
      console.log('clickHandle:', msg, ev)
    }
  },

  created () {

  }
}

</script>

<style>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.welcome{
    margin-top:50px;
}
.usermotto {
    width:200px;
    height: 70px;
    color: #fff;
    text-align: center;
    line-height:70px;
    margin-top: 150px;
    background-color: #2196f3;
    display: inline-block;
    overflow: hidden;
    position: relative;
    border-radius: 2px;
    box-shadow: 0 1px 6px rgba(0,0,0,.117647), 0 1px 4px rgba(0,0,0,.117647);
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}

.description{
    position: fixed;
    bottom: 60px;
}
</style>
