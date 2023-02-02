<template>
  <div
    id="app"
    style="
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 50px;
    "
  >
    <div style="margin: -10px">
      <!-- 房屋设计 -->
      <div>
        <span>单位：cm</span>
        <br />
        <span>注：默认墙体厚度20</span>
      </div>
      <!-- 整个房子 -->
      <div class="home">
        <div class="w s-s" style="height: 840px;top:80px;"></div>
        <!-- 墙柜素材 -->
        <el-popover
          placement="bottom"
          title="装修参考"
          width="300"
          trigger="click">
          <el-carousel height="300px" :autoplay="false">
            <el-carousel-item v-for="item in 2" :key="item" style="height:300px">
              <img :src="`./qianggui/${item}.jpg`" alt="" style="height: 100%">
            </el-carousel-item>
          </el-carousel>
          <i slot="reference" class="magic el-icon-magic-stick" style="top: 380px;left: 20px;"></i>
        </el-popover>
        <!-- 阳台素材 -->
        <el-popover
          placement="bottom"
          title="装修参考"
          width="300"
          trigger="click">
          <el-carousel height="300px" :autoplay="false">
            <el-carousel-item v-for="item in 2" :key="item" style="height:300px">
              <img :src="`./yangtai/${item}.jpg`" alt="" style="height: 100%">
            </el-carousel-item>
          </el-carousel>
          <i slot="reference" class="magic el-icon-magic-stick" style="top: 850px;left: 85px;"></i>
        </el-popover>
        <!-- 洗手间素材 -->
        <el-popover
          placement="bottom"
          title="装修参考"
          width="300"
          trigger="click">
          <el-carousel height="300px" :autoplay="false">
            <el-carousel-item v-for="item in 2" :key="item" style="height:300px">
              <img :src="`./xishoujian/${item}.jpg`" alt="" style="height: 100%">
            </el-carousel-item>
          </el-carousel>
          <i slot="reference" class="magic el-icon-magic-stick" style="top: 423px;left: 417px;"></i>
        </el-popover>
        <div class="normal-wall show-border s-s" style="width: 178px;top:70px;left: 10px;"></div>
        <div class="w s-s" style="width: 80px;top:920px;border-right: none"></div>
        <div class="normal-wall show-border s-s" style="height: 118px;top:930px;left: 50px;"></div>
        <div class="normal-wall show-border s-s" style="height: 118px;top:930px;left: 520px;"></div>
        <div class="w s-s" style="width: 105px;top:80px;top:920px;left: 515px;"></div>
        <div class="w s-s" style="width: 65px;top:80px;top:920px;left: 620px;"></div>
        <div class="normal-wall show-border s-s" style="width: 63px;top:910px;left: 875px;"></div>
        <div class="normal-wall show-border s-s" style="height: 468px;top:440px;left: 920px;"></div>
        <div class="w s-s" style="height: 190px;top:250px;left: 930px;border-bottom: none;"></div>
        <div class="w s-s" style="width: 70px;top:250px;left: 870px;border-left: none;"></div>
        <div class="normal-wall show-border s-s" style="width: 228px;top:240px;left: 630px;"></div>
        <!-- 书房主卧分割墙 -->
        <div class="w s-s" style="height: 300px;top:80px;top:620px;left: 620px;"></div>
        <div class="w s-s" style="width: 490px;top:1060px;left: 40px;"></div>
        <!-- 横梁 -->
        <div class="bridge s-s show-border" style="width: 168px;left: 10px; top: 260px;"></div>
        <div class="bridge s-s show-border" style="height: 550px;left: 340px; top: 500px;"></div>
        <!-- 厨房 -->
        <div class="kitchen">
          <!-- 墙壁 -->
          <div class="w s-s" style="width: 240px"></div>
          <div class="w s-s" style="height: 250px; left: 100%"></div>
          <div class="w s-s" style="width: 80px; left: 160px; top: 250px"></div>
          <div class="w s-s" style="height: 20px; left: 160px; top: 250px"></div>
          <div class="normal-wall show-border s-s" style="width: 158px; top: 260px;left:-10px;"></div>
          <div class="normal-wall show-border s-s" style="height: 88px; left: -10px;top:10px;"></div>
          <div class="normal-wall show-border s-s" style="height: 13px; top: 245px; left: -10px;"></div>
          <!-- 线 -->
          <div class="l s-s" style="width: 170px; left: 10px; top: 60px"></div>
          <div class="l s-s" style="width: 50px; left: 180px; top: 60px"></div>
          <div class="l s-s" style="height: 50px; left: 180px; top: 10px"></div>
          <div class="l s-s" style="height: 130px; left: 180px; top: 60px"></div>
          <div class="l s-s" style="width: 70px; left: 110px; top: 190px"></div>
          <div class="l s-s" style="width: 50px; left: 180px; top: 190px"></div>
          <div class="l s-s" style="height: 50px; left: 180px; top: 190px"></div>
          <div class="l s-s" style="height: 70px; left: 110px; top: 190px"></div>
          <!-- 冰箱 -->
          <div class="freezer s-s"></div>
          <!-- 门 -->
          <div
            class="doors"
            style="width: 16px;height: 160px;position:absolute;top: 100px;left: -8px;"
          >
            <div class="d s-s" style="height: 75px;"></div>
            <div class="d s-s" style="height: 75px;left: 8px;top: 70px"></div>
          </div>
        </div>
        <!-- 洗手间 -->
        <div class="washroom">
          <!-- 厚墙 -->
          <div
            class="w s-s"
            style="height: 220px;top: 20px; border-top: none;margin-top: 0;"
          ></div>
          <div class="w s-s" style="width: 190px;left: 80px; margin-left: 0;border-left: 0;"></div>
          <!-- 薄墙 -->
          <div class="w-thin s-s show-border" style="height: 228px;left: 260px; top: 10px;"></div>
          <div class="w-thin s-s show-border" style="height: 228px;left: 140px; top: 10px;"></div>
          <div class="w-thin s-s show-border" style="width: 128px;left: 10px; top: 110px;"></div>
          <div class="w-thin s-s show-border" style="width: 258px;left: 10px; top: 240px;"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  mounted() {
    Array.prototype.forEach.call(
      document.getElementsByClassName("s-s"),
      element => {
        const borderLength = element.className.indexOf('show-border') > -1 ? 2 : 0
        const clientWidth = element.clientWidth + borderLength
        const clientHeight = element.clientHeight + borderLength
        const widthHeightArray = [clientWidth, clientHeight];
        element.setAttribute(
          "datasize",
          widthHeightArray.filter(num => num > 1).join("*")
        );
      }
    );
  }
};
</script>

<style lang="less" scoped>
@import './style/common.less';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

/* 门 */
.d {
  width: 7px;
  height: 7px;
  background-color: #aaa;
  position: absolute;
}
/* 房屋 */
.home {
  margin-top: 20px;
  width: 930px;
  height: 1060px;
  border: 1px solid #eee;
  position: relative;
}
/* 厨房 */
.kitchen {
  width: 240px;
  height: 270px;
  position: absolute;
  left: 190px;
  .freezer {
    width: 92px;
    height: 64px;
    border: 1px solid #aaa;
    position: absolute;
    left: 13px;
    bottom: 13px;
  }
}
/* 卫生间 */
.washroom {
  width: 270px;
  height: 240px;
  position: absolute;
  left: 350px;
  top: 250px;
}
</style>
