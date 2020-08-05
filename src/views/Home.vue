<template>
  <div class="home">
    <TopBar></TopBar>
    <div class="container">
        <div class="left-nav">
          <LeftNav></LeftNav>
        </div>
        <div class="body">
          <div class="send-box">
            <SendBox></SendBox>
          </div>
        </div>
        <div class="right-panel">

        </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import TopBar from '@/components/topBar.vue'
import LeftNav from '@/components/leftNav.vue'
import SendBox from '@/components/sendBox.vue'
export default {
  name: 'Home',
  components: {
    TopBar,
    LeftNav,
    SendBox
  }
}
</script>
<style lang="less" socpe>
  .home{
    .container{
      width: 1170px;
      margin: 16px auto 0;
      .left-nav,.body{
        float: left;
      }
      .left-nav{
        width: 110px;
        margin-right: 30px;
      }
      .body{
        width: 660px;
        .send-box{
          border: 1px solid #e8e8e8 ;
        }

      }
      .right-panel{
        float: right;
        width: 340px;
        background-color: violet;
        height: 50vh;
      }
    }
    
  }
  
</style>