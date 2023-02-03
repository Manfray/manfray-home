<template>
  <div id="app" style="padding: 10px;">
    <div style="margin: -10px">
      <!-- 房屋设计 -->
      <div>
        <span>单位：cm</span>
        <br />
        <span>注：默认墙体厚度20</span>
        <br />
        <span>显示用电器件</span>
        <el-switch
          v-model="showDianqiList"
          active-color="red">
        </el-switch>
        <span>显示用水器件</span>
        <el-switch
          v-model="showWaterList"
          active-color="blue">
        </el-switch>
        <div>
          备注：<br/>
          1、阳台到沙发和书桌中间的位置怎么设计；<br/>
          2、阳台的洗衣机摆放位置;<br/>
          3、阳台操作台怎么设计，比如洗手池（一定要吗），做个架子？，下面做个拖把清洗槽？
        </div>
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
          <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
            <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
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
          <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
            <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
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
          <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
            <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
              <img :src="`./xishoujian/${item}.jpg`" alt="" style="height: 100%">
            </el-carousel-item>
          </el-carousel>
          <i slot="reference" class="magic el-icon-magic-stick" style="top: 423px;left: 417px;"></i>
        </el-popover>
        <div class="normal-wall show-border s-s" style="width: 178px;top:70px;left: 10px;"></div>
        <div class="w v s-s" style="width: 80px;top:920px;border-right: none"></div>
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
        <div class="bridge s-s show-border" style="width: 168px;left: 10px; top: 240px;"></div>
        <div class="bridge s-s show-border" style="height: 550px;left: 340px; top: 500px;"></div>
        <!-- 厨房 -->
        <div class="kitchen">
          <!-- 墙壁 -->
          <div class="w s-s" style="width: 240px"></div>
          <div class="w s-s" style="height: 85px; left: 100%;border-bottom: none;"></div>
          <div class="normal-wall show-border s-s" style="height: 108px; left: 230px;top: 85px;">
            <div class="dianqi-name">窗户</div>
          </div>
          <div class="w s-s" style="height: 55px; left: 100%;top: 205px;border-top: none;"></div>
          <div class="w s-s" style="width: 80px; left: 160px; top: 250px"></div>
          <div class="w s-s" style="height: 20px; left: 160px; top: 250px"></div>
          <div class="normal-wall show-border s-s" style="width: 158px; top: 260px;left:-10px;"></div>
          <div class="normal-wall show-border s-s" style="height: 88px; left: -10px;top:10px;"></div>
          <div class="normal-wall show-border s-s" style="height: 13px; top: 245px; left: -10px;"></div>
          <!-- 线 -->
          <div class="l s-s" style="width: 158px; left: 10px; top: 60px"></div>
          <div class="l s-s" style="width: 62px; left: 168px; top: 60px"></div>
          <div class="l s-s" style="height: 50px; left: 168px; top: 10px"></div>
          <div class="l s-s" style="height: 140px; left: 168px; top: 60px"></div>
          <div class="l s-s" style="width: 58px; left: 110px; top: 200px"></div>
          <div class="l s-s" style="width: 100px; left: 10px; top: 200px"></div>
          <div class="l s-s" style="width: 62px; left: 168px; top: 200px"></div>
          <div class="l s-s" style="height: 40px; left: 168px; top: 200px"></div>
          <div class="l s-s" style="height: 60px; left: 110px; top: 200px"></div>
          <!-- 冰箱 -->
          <div class="freezer s-s"></div>
          <!-- 排烟管道 -->
          <div class="paiyanguandao s-s">
            <div class="dianqi-name">排烟管道</div>
          </div>
          <!-- 油烟机 -->
          <div class="youyanji s-s">
            <div class="dianqi-name">油烟机</div>
          </div>
          <!-- 燃气灶 -->
          <div class="ranqizao s-s">
            <div class="dianqi-name">燃气灶</div>
          </div>
          <!-- 洗碗机 -->
          <div class="xiwanji s-s">
            <div class="dianqi-name">洗碗机</div>
            <el-popover
              placement="bottom"
              title="装修参考"
              width="300"
              trigger="click">
              <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
                <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
                  <img :src="`./xiwanji/${item}.jpg`" alt="" style="height: 100%">
                </el-carousel-item>
              </el-carousel>
              <i slot="reference" class="magic el-icon-magic-stick" style="top: 20px;left: 10px;"></i>
            </el-popover>
          </div>
          <!-- 洗手池 -->
          <div class="xishouchi s-s">
            <div class="dianqi-name">洗手池</div>
            <el-popover
              placement="bottom"
              title="装修参考"
              width="300"
              trigger="click">
              <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
                <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
                  <img :src="`./xishouchi/${item}.jpg`" alt="" style="height: 100%">
                </el-carousel-item>
              </el-carousel>
              <i slot="reference" class="magic el-icon-magic-stick" style="top: 20px;left: 10px;"></i>
            </el-popover>
          </div>
          <!-- 储物架 -->
          <div class="chuwujia s-s">
            <div class="dianqi-name">储物架</div>
            <el-popover
              placement="bottom"
              title="装修参考"
              width="300"
              trigger="click">
              <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
                <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
                  <img :src="`./bingxiang/${item}.jpg`" alt="" style="height: 100%">
                </el-carousel-item>
              </el-carousel>
              <i slot="reference" class="magic el-icon-magic-stick" style="top: 0px;left: 37px;"></i>
            </el-popover>
          </div>
          <!-- 门 -->
          <div
            class="doors"
            style="width: 16px;height: 160px;position:absolute;top: 100px;left: -8px;"
          >
            <div class="d s-s" style="height: 75px;"></div>
            <div class="d s-s" style="height: 75px;left: 8px;top: 70px"></div>
          </div>
          <!-- 厨房电器 -->
          <div class="dianqi-list s-s" v-show="showDianqiList">
            厨房用电器件：
            <div>煤气灶</div>
            <div>油烟机</div>
            <div>洗碗机</div>
            <div>净水器</div>
            <div>热水器</div>
            <div>冰箱</div>
            <div>灯</div>
            <div>额外插座</div>
          </div>
          <div class="dianqi-list dl-water s-s" v-show="showWaterList">
            厨房用水器件：
            <div>洗碗机</div>
            <div>净水器</div>
            <div>热水器</div>
            <div>洗菜槽的水龙头</div>
          </div>
        </div>
        <div class="zoulang">
          <!-- 玄关 -->
          <div class="xuanguan s-s"></div>
          <!-- 玄关素材 -->
          <el-popover
            placement="bottom"
            title="装修参考"
            width="300"
            trigger="click">
            <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
              <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
                <img :src="`./xuanguan/${item}.jpg`" alt="" style="height: 100%">
              </el-carousel-item>
            </el-carousel>
            <i slot="reference" class="magic el-icon-magic-stick" style="top: 69px;left: 102px;"></i>
          </el-popover>
          <!-- 走廊电器 -->
          <div class="dianqi-list s-s" v-show="showDianqiList">
            走廊用电器件：
            <div>开关</div>
            <div>额外插座</div>
            <div>灯</div>
          </div>
        </div>
        <!-- 大厅 -->
        <div class="dating">
          <!-- 壁柜 -->
          <div class="bigui s-s"></div>
          <!-- 餐桌 -->
          <div class="canzhuo s-s">
            <div class="dianqi-name">餐桌</div>
          </div>
          <!-- 电视65寸：144*81 -->
          <div class="dianshi-loukong s-s">
            <div class="dianqi-name">电视柜</div>
          </div>
          <div class="dianshi s-s">
            <div class="dianqi-name">电视</div>
          </div>
          <div class="dianshi-cegui s-s">
            <div class="dianqi-name">侧柜</div>
          </div>
          <div class="shafa s-s" :class="switchTable ? 'open' : 'close'">
            <div class="dianqi-name">沙发</div>
          </div>
          <!-- 空调 -->
          <div class="kongtiao s-s">
            <div class="dianqi-name">空调</div>
            <el-popover
              placement="bottom"
              title="装修参考"
              width="300"
              trigger="click">
              <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
                <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
                  <img :src="`./kongtiao/${item}.jpg`" alt="" style="height: 100%">
                </el-carousel-item>
              </el-carousel>
              <i slot="reference" class="magic el-icon-magic-stick" style="top: 10px;left: 35px;"></i>
            </el-popover>
          </div>
          <div class="dianqi-list s-s" v-show="showDianqiList">
            大厅用电器件：
            <div>电视机</div>
            <div>立式空调</div>
            <div>开关</div>
            <div>额外插座</div>
            <div>射灯、吸顶灯</div>
          </div>
          <div class="mark-line h s-s" style="height: 105px;top:240px;left: 332px"></div>
        </div>
        <!-- 阳台 -->
        <div class="yangtai">
          <!--  -->
          <div class="yanggaiguizi s-s"></div>
          <div class="xiyiji s-s">
            <div class="dianqi-name">洗衣机 、 烘干机</div>
            <el-popover
              placement="bottom"
              title="装修参考"
              width="300"
              trigger="click">
              <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
                <el-carousel-item v-for="item in 10" :key="item" style="height:300px">
                  <img :src="`./xiyiji/${item}.jpg`" alt="" style="height: 100%">
                </el-carousel-item>
              </el-carousel>
              <i slot="reference" class="magic el-icon-magic-stick" style="top: 10px;left: 10px;"></i>
            </el-popover>
          </div>
          <div class="dianqi-list s-s" v-show="showDianqiList">
            阳台用电器件：
            <div>洗衣机</div>
            <div>烘干机</div>
            <div>电动晾衣架？</div>
            <div>开关</div>
            <div>额外插座</div>
            <div>灯</div>
          </div>
          <div class="dianqi-list dl-water s-s" v-show="showWaterList">
            阳台用水器件：
            <div>洗衣机</div>
            <div>水槽的水龙头</div>
          </div>
        </div>
        <!-- 书房 -->
        <div class="shufang">
          <!--  -->
          <div class="zhuozi s-s" :class="switchTable ? 'open' : 'close'">
            <div class="dianqi-name">桌子</div>
            切换
            <el-switch
              v-model="switchTable"
              active-color="yellow">
            </el-switch>
          </div>
          <div class="shujia s-s">
            <div class="dianqi-name">书架</div>
          </div>
          <div class="dianqi-list s-s" v-show="showDianqiList">
            书房用电器件：
            <div>电脑</div>
            <div>射灯</div>
            <div>电动晾衣架？</div>
            <div>开关</div>
            <div>额外插座</div>
            <div>射灯、吸顶灯</div>
          </div>
          <!-- 标线 -->
          <div v-show="switchTable" class="mark-line v s-s" style="width: 70px;top:137px;left: 133px"></div>
          <div v-show="switchTable" class="mark-line v s-s" style="width: 70px;top:137px;left: -33px"></div>
          <div v-show="switchTable" class="mark-line h s-s" style="height: 60px; top:237px;left: 124px"></div>
        </div>
        <!-- 主卧 -->
        <div class="zhuwo">
          <!--  -->
          <div class="yigui s-s"></div>
          <div class="dianqi-list s-s" v-show="showDianqiList">
            主卧用电器件：
            <div>投影仪</div>
            <div>开关</div>
            <div>额外插座</div>
            <div>吸顶灯、床头灯</div>
          </div>
        </div>
        <!-- 次卧 -->
        <div class="ciwo">
          <!--  -->
          <div class="yigui s-s"></div>
          <div class="dianqi-list s-s" v-show="showDianqiList">
            次卧用电器件：
            <div>开关</div>
            <div>额外插座</div>
            <div>吸顶灯、床头灯</div>
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
          <!-- 用电用水 -->
          <div class="dianqi-list s-s" v-show="showDianqiList">
            洗手间用电器件：
            <div>开关</div>
            <div>额外插座</div>
            <div>吸顶灯、床头灯</div>
          </div>
          <div class="dianqi-list dl-water s-s" v-show="showWaterList">
            洗手间用水器件：
            <div>洗脸盆水龙头</div>
            <div>卫生间马桶</div>
            <div>洗澡间喷头</div>
            <div>洗澡间蹲便</div>
            <div>洗拖把水龙头</div>
          </div>
        </div>
        <!-- 辅助线 -->
        <div class="fzx fzx-x" style="width: 100%;top: 500px;"></div>
        <div class="fzx fzx-x" style="width: 100%;top: 610px;"></div>
        <div class="fzx fzx-y" style="height: 100%;"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      showDianqiList: false,
      showWaterList: false,
      switchTable: false,
    }
  },
  watch: {
    showDianqiList(val) {
      this.reRenderBoxSize(val)
    },
    switchTable(val) {
      this.reRenderBoxSize(val)
    }
  },
  mounted() {
    this.setBoxSize()
  },
  methods: {
    reRenderBoxSize(val) {
      val && setTimeout(() => {
        this.setBoxSize()
      }); 
    },
    setBoxSize() {
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
  }
};
</script>

<style lang="less" scoped>
@import './style/common.less';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
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
    bottom: 11px;
  }
  .paiyanguandao { // 排烟管道
    width: 45px;
    height: 45px;
    border: 1px solid #aaa;
    position: absolute;
    left: 10px;
    top: 10px;
  }
  .youyanji { // 油烟机
    width: 90px;
    height: 43px;
    border: 1px solid #aaa;
    position: absolute;
    left: 60px;
    top: 12px;
  }
  .ranqizao {
    width: 60px;
    height: 38px;
    border: 1px solid #aaa;
    position: absolute;
    left: 75px;
    top: 14px;
  }
  .xiwanji {
    width: 60px;
    height: 60px;
    border: 1px solid #aaa;
    position: absolute;
    left: 169px;
    top: 61px;
  }
  .xishouchi {
    width: 45px;
    height: 75px;
    border: 1px solid #aaa;
    position: absolute;
    left: 175px;
    top: 124px;
  }
  .chuwujia {
    width: 54px;
    height: 36px;
    border: 1px solid #aaa;
    position: absolute;
    left: 112px;
    top: 202px;
  }

}
// 走廊
.zoulang {
  width: 170px;
  height: 150px;
  position: absolute;
  left: 10px;
  top: 90px;
  .xuanguan {
    width: 40px;
    height: 150px;
    border: 1px solid #aaa;
    position: absolute;
    left: 0px;
    top: 0px;
  }
}
.dating {
  width: 330px;
  height: 650px;
  position: absolute;
  left: 10px;
  top: 260px;
  .bigui {
    width: 40px;
    height: 650px;
    border: 1px solid #aaa;
    position: absolute;
    left: 0px;
    top: 0px;
  }
  .canzhuo {
    width: 140px;
    height: 70px;
    border: 1px solid #aaa;
    position: absolute;
    left: 190px;
    top: 95px;
  }
  .dianshi-loukong {
    width: 40px;
    height: 180px;
    border: 1px solid #aaa;
    position: absolute;
    left: 0px;
    top: 380px;
  }
  .dianshi {
    width: 10px;
    height: 150px;
    border: 1px solid #aaa;
    position: absolute;
    left: 3px;
    top: 395px;
  }
  .dianshi-cegui {
    width: 40px;
    height: 40px;
    border: 1px solid #aaa;
    position: absolute;
    left: 0px;
    top: 560px;
  }
  .shafa {
    width: 90px;
    height: 225px;
    border: 1px solid #aaa;
    position: absolute;
    left: 260px;
    top: 360px;
    &.open {
      left: 225px;
    }
  }
  .kongtiao {
    width: 43px;
    height: 43px;
    border: 1px solid #aaa;
    border-radius: 50%;
    position: absolute;
    left: 2px;
    top: 604px;
  }
}
.yangtai {
  width: 450px;
  height: 120px;
  position: absolute;
  left: 69px;
  top: 930px;
  .yanggaiguizi {
    width: 70px;
    height: 132px;
    border: 1px solid #aaa;
    border-top-left-radius: 19px;
    position: absolute;
    top: -20px;
    right: 0px;
  }
  .xiyiji {
    width: 63px;
    height: 60px;
    border: 1px solid #aaa;
    position: absolute;
    top: 50px;
    right: 3px;
  }
}
.shufang {
  width: 250px;
  height: 300px;
  position: absolute;
  left: 360px;
  top: 610px;
  .shujia {
    width: 40px;
    height: 300px;
    border: 1px solid #aaa;
    position: absolute;
    top: 0px;
    right: 0px;
  }
  .zhuozi {
    width: 90px;
    height: 225px;
    border: 1px solid #aaa;
    position: absolute;
    left: 0px;
    top: 10px;
    &.open {
      left: 40px;
    }
  }
}
.zhuwo {
  width: 290px;
  height: 365px;
  position: absolute;
  left: 630px;
  top: 545px;
  // background-color: #eee;
  .yigui {
    width: 180px;
    height: 65px;
    border: 1px solid #aaa;
    position: absolute;
    top: 0px;
    right: 0px;
  }
}
.ciwo {
  width: 300px;
  height: 290px;
  position: absolute;
  left: 620px;
  top: 260px;
  // background-color: #eee;
  .yigui {
    width: 180px;
    height: 65px;
    border: 1px solid #aaa;
    position: absolute;
    bottom: 0;
    right: 0;
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
