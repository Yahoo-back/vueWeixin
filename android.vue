<!--下载链接页 -->
<template>
  <div>
    <!-- <div>请按照说明操作，否则无法正常使用APP</div> -->
     <div id="ts" v-if="title">
            <span class="ts">请点击右上角选择"浏览器中打开"</span>
            <div class="kongxin"></div>
        </div>
        <van-loading v-if="loading" type="spinner" style="margin-top: 70px;position: absolute; width: 30%; margin-left: 35%" vertical>加载中...</van-loading>
	<div>
    	<img class="azlogo" src="../../assets/image/logo.png">
      <div class="logoName">小鲨分期</div>
    </div>
     <van-button v-if="wxBtn" @click="wxaz()" class="buttona" size="large">点击安装</van-button>
    <van-button v-if="llqBtn" @click="az()" class="buttona" size="large">点击安装</van-button>
  </div>
</template>

<script>
import {Dialog,Loading } from 'vant';
export default {
  name: 'downLoad',
    data(){
    return{
      title: false,
      wxBtn: false,
      llqBtn: false,
      loading: false,
    }
  },
	created () {
    var ua = navigator.userAgent.toLowerCase();
    //微信
    if (ua.match(/MicroMessenger/i) == "micromessenger") {
      this.title = true
      this.wxBtn = true
    } 
    //浏览器
    else {
      this.title = false;
      this.llqBtn = true;
    }
},

  methods:{
    wxaz(){
         Dialog.alert({
                    title: '温馨提示',
                    message: '微信/QQ内无法下载应用,请点击右上角选择"浏览器中打开"'
                  }).then(() => {
                  });
    },
    az(){
      window.location.href=""
       this.loading = true;
       var that = this;
         setTimeout(function(){
                         that.loading = false;
                    },4000)
    },
  }
}

</script>

<style lang="less">
#ts{
    width:100px;
    height:40px;
    position:absolute;
    top: 2%;
    right: 2%;  
    border:2px solid #00a8fd;
    border-radius:8px;
    background: #00a8fd;
}
.ts{
    font-size: 12px;
    color: #f1f1f1;
    padding: 0 4px;
}
.kongxin{
    width:0;
    height:0;
    border:6px solid transparent;
    border-bottom-color:#00a8fd;
    position: relative;
    top: -136%;
    left:87%;
}
.banner{
    // margin-top: 80px;
}
.logoName{
    margin-top: 20px;
    text-align: center;
    font-size: 20px;
    font-weight: bold;
    letter-spacing: 1px;
}
.azlogo{
    // margin: 0 auto;
    width: 40%;
    height: 40%;
    margin-left: 5%;
    margin-top: 150px;
}
.buttona{
  margin-top: 30px;
  background: #00a8fd;
  border-radius: 3px;
  color: #fff;
  width: 140px;
  height: 50px;
  border: 1px solid #00a8fd;
}
.info{
    margin-top: 20px;
    // color: #3774f8;
    font-weight: bold;
    font-size: 15px;
}
.intro{
  margin-top: 20px;
  text-align: left;
  padding: 10px 25px;
  font-size: 15px;
}
.bottomImg{
  padding: 10px 25px;
}
.b1{
  margin-top: 20px;
}
</style>
