<!--下载链接页 -->
<template>
  <div class="downLoad">
    <img src="../../assets/image/bgBlue.png">
    <img src="../../assets/image/bg.png" class="alertbg"/>
    <div class="alertImg">
      <img src="../../assets/image/alert_bg.png"  alt=""/>
      <van-button  @click="iosDownLoad()" class="left" size="large"><img style="width: 32px;height: 32px; margin-top: 5px" src="../../assets/image/pg1.png"/>IOS下载</van-button>
      <van-button  @click="androidDownLoad()" class="right" size="large"><img style="width: 32px;height: 32px; margin-top: 5px" src="../../assets/image/az123.png"/>安卓下载</van-button>
    </div>      
  </div>
</template>

<script>
export default {
  name: 'downLoad',
  data() {
    return {
    }
	},
	created () {
},

  methods:{
		iosDownLoad(){
      this.$router.replace('/ios')
		},
		androidDownLoad(){
       this.$router.replace('/android')
		}
  }
}

</script>

<style lang="less">
.downLoad{
  background: #1d4bde;
  position: relative;
  height: 100%;
  padding-bottom: 200px;
}
.xz{
  font-size: 18px;
  height: 32px;
  line-height: 32px;
}
.alertbg{
  position: relative;
  margin-top: -65%;
}
.alertImg{
  position: relative;
  margin-top: -85%;
}
.left{
  font-size: 18px;
  color: #fff;
  background: #3e43ea;
  position: relative;
  margin-left: 13%;
  width: 35%;
  float: left;
  margin-top: -25%;
  border: #3e43ea;
}
.right{
  font-size: 18px;
  color: #fff;
  position: relative;
  margin-left: 5%;
  width: 35%;
  margin-right: 13%;
  float: right;
  margin-top: -25%;
  background: #0bb710;
  border: #0bb710;
}
</style>


