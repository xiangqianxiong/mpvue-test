<template>
  <div>
    <div class="head">
      头部轮播图
      <swiper :images="images" />
    </div>
    <div class="body">
      主体图片
    </div>
    <div class="foot">
      尾部文字
    </div>
  </div>
</template>

<script>

import swiper from '@/components/swiper'

export default {
  data () {
    return {
      motto: 'Hello 相乾雄、田昌华',
      userInfo: {
        nickName: 'mpvue123456',
        avatarUrl: 'https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png'
      },
      images: [
        {
          url:
            'https://img-oss.yunshanmeicai.com/goods/default/31d8dfa4-0d7b-4694-80f9-41b07c9d0a3a.png',
          index: 1
        },
        {
          url:
            'https://img-oss.yunshanmeicai.com/goods/default/e83c8f0f-4acc-4729-bcbb-294f2b314977.jpg',
          index: 2
        }
      ]
    }
  },

  components: {
    swiper
  },

  methods: {
    bannerClick (data) {
      console.log(data)
    },
    bindViewTap () {
      const url = '../self/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
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

.counter{
  height: 100rpx;
  font-size: 20rpx;
}
.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}
.all{
  width:7.5rem;
  height:1rem;
  background-color:blue;
}
.all:after{
  display:block;
  content:'';
  clear:both;
}
.left{
  float:left;
  width:3rem;
  height:1rem;
  background-color:red;
}

.right{
  float:left;
  width:4.5rem;
  height:1rem;
  background-color:green;
}
</style>
