<template>
  <div id="app" style="padding: 20px 50px; width: 930px;">
    <div>
      <!-- 房屋设计 -->
      <div>
        <span>单位：cm</span>
        <br />
        <span>注：默认墙体厚度20</span>
        <br />
        <h3>房屋布局控制</h3>
        <div style="padding-left: 20px">
          <span>显示用电器件</span>
          <el-switch
            v-model="showDianqiList"
            active-color="red">
          </el-switch><br/>
          <span>显示用水器件</span>
          <el-switch
            v-model="showWaterList"
            active-color="blue">
          </el-switch><br/>
          <span>阳台洗衣机靠左</span>
          <el-switch
            v-model="xiyijiAlignleft"
            active-color="green">
          </el-switch><br/>
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
        <div class="normal-wall show-border s-s" style="width: 178px;top:70px;left: 10px;"></div>
        <div class="w v s-s" style="width: 80px;top:920px;border-right: none"></div>
        <div class="normal-wall show-border s-s" style="height: 48px;top:930px;left: 50px;"></div>
        <div class="normal-wall show-border s-s" style="height: 48px;top:930px;left: 520px;"></div>
        <div class="w s-s" style="width: 105px;top:80px;top:920px;left: 515px;"></div>
        <div class="w s-s" style="width: 65px;top:80px;top:920px;left: 620px;"></div>
        <div class="normal-wall show-border s-s" style="width: 63px;top:910px;left: 875px;"></div>
        <div class="normal-wall show-border s-s" style="height: 468px;top:440px;left: 920px;"></div>
        <div class="w s-s" style="height: 190px;top:250px;left: 930px;border-bottom: none;"></div>
        <div class="w s-s" style="width: 70px;top:250px;left: 870px;border-left: none;"></div>
        <div class="normal-wall show-border s-s" style="width: 228px;top:240px;left: 630px;"></div>
        <!-- 书房主卧分割墙 -->
        <div class="w s-s" style="height: 300px;top:80px;top:620px;left: 620px;"></div>
        <!-- <div class="w s-s" style="width: 490px;top:1060px;left: 40px;"></div> -->
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
        <!-- 走廊 -->
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
          <img src="../public/common/men.jpg" alt="" class="men">
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
          <div class="dianqi-list dl-water s-s" v-show="showWaterList">
            大厅用水器件：
            <div>暖气片</div>
          </div>
          <div class="mark-line h s-s" style="height: 105px;top:240px;left: 332px"></div>
          <div class="mark-line h s-s" style="height: 70px;top:167px;left: 216px"></div>
          <div class="mark-line h s-s" style="height: 70px;top:20px;left: 216px"></div>
        </div>
        <!-- 阳台 -->
        <div class="yangtai" :class="xiyijiAlignleft ? 'align-left' : 'align-right'">
          
          <div class="normal-wall show-border s-s" style="width: 47px;top: -20px;left: 247px;"></div>
          <div class="add-wall normal-wall show-border s-s" style="width: 55px;top: -20px;left: 379px;"></div>
          <div class="normal-wall show-border s-s" style="width: 90px;top: 120px;left: -40px;"></div>
          <div class="chuanghu show-border s-s" style="width: 420px;top: 120px;left: 50px;"></div>
          <div class="chuanghu show-border s-s" style="height: 70px;top: 50px;left: 450px;"></div>
          <div class="chuanghu show-border s-s" style="height: 70px;top: 50px;left: -20px;"></div>
          <!--  -->
          <div class="yangtaiguizi s-s"></div>
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
            <div>暖气片?</div>
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
          <div class="dianqi-list dl-water s-s" v-show="showWaterList">
            书房用水器件：
            <div>暖气片</div>
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
          <div class="dianqi-list dl-water s-s" v-show="showWaterList">
            主卧用水器件：
            <div>暖气片</div>
          </div>
          <div class="w-thin s-s show-border" style="height: 130px;left: 100px; top: -66px;"></div>
          <img src="../public/common/men.jpg" alt="" class="men">
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
          <div class="dianqi-list dl-water s-s" v-show="showWaterList">
            次卧用水器件：
            <div>暖气片</div>
          </div>
          <img src="../public/common/men.jpg" alt="" class="men">
        </div>
        <!-- 洗手间 -->
        <div class="washroom">
          <div class="xiashuiguan s-s">
            <div class="dianqi-name">污水管</div>
          </div>
          <!-- 厚墙 -->
          <div
            class="w s-s"
            style="height: 220px;top: 20px; border-top: none;margin-top: 0;"
          ></div>
          <div class="w s-s" style="width: 190px;left: 80px; margin-left: 0;border-left: 0;"></div>
          <!-- 薄墙 -->
          <div class="w-thin s-s show-border" style="height: 228px;left: 260px; top: 10px;"></div>
          <div class="w-thin s-s show-border" style="height: 228px;left: 140px; top: 10px;"></div>
          <div class="w-thin s-s show-border" style="width: 128px;left: 10px; top: 109px;"></div>
          <div class="w-thin s-s show-border" style="width: 258px;left: 10px; top: 240px;"></div>

          <img src="../public/common/men.jpg" alt="" class="men men1"/>
          <img src="../public/common/men.jpg" alt="" class="men men2"/>
          <div class="matong s-s"></div>
          <div class="xishouchi s-s">
            <div class="dianqi-name">洗手池</div>
          </div>
          <div class="muyu s-s">
            <div class="dianqi-name">洗澡间</div>
          </div>
          <div class="dunbian s-s">
            <div class="dianqi-name">蹲便</div>
          </div>
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
          <!-- 洗手池素材 -->
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
            <i slot="reference" class="magic el-icon-magic-stick" style="top: 177px;left: 70px;"></i>
          </el-popover>
          <!-- 马桶素材 -->
          <el-popover
            placement="bottom"
            title="装修参考"
            width="300"
            trigger="click">
            <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
              <el-carousel-item v-for="item in 2" :key="item" style="height:300px">
                <img :src="`./matong/${item}.jpg`" alt="" style="height: 100%">
              </el-carousel-item>
            </el-carousel>
            <i slot="reference" class="magic el-icon-magic-stick" style="top: 57px;left: 70px;"></i>
          </el-popover>
          <!-- 洗澡间 -->
          <el-popover
            placement="bottom"
            title="装修参考"
            width="300"
            trigger="click">
            <el-carousel height="300px" :autoplay="false" arrow="always" indicator-position="none">
              <el-carousel-item v-for="item in 4" :key="item" style="height:300px">
                <img :src="`./xizaojian/${item}.jpg`" alt="" style="height: 100%">
              </el-carousel-item>
            </el-carousel>
            <i slot="reference" class="magic el-icon-magic-stick" style="top: 109px;left: 190px;"></i>
          </el-popover>
        </div>
        <!-- 辅助线 -->
        <div class="fzx fzx-x" style="width: 100%;top: 500px;"></div>
        <div class="fzx fzx-x" style="width: 100%;top: 555px;"></div>
        <div class="fzx fzx-x" style="width: 100%;top: 610px;"></div>
        <div class="fzx fzx-y" style="height: 100%;"></div>
      </div>
      <!-- 疑问笔记 -->
      <div>
        <h3>问题备注</h3>
        - 洗拖把的地方放哪里？<br/>
        - 阳台到沙发和书桌中间的位置怎么设计；<br/>
        - 阳台的洗衣机摆放位置（靠窗还是靠客厅）;<br/>
        - 阳台操作台怎么设计，比如洗手池（一定要吗），做个架子？，下面做个拖把清洗槽？<br/>
        - 阳台中间柱子如果是承重墙，解决方案：把洗衣机挪走<br/>
        <div style="padding-left: 20px">
          1：洗衣机靠阳台西边（被隔开的小门就能显得大点）<br/>
          2：洗衣机烘干机放到洗手间<br/>
          3：洗衣机烘干机放到立式空调位置<br/>
          4：洗衣机烘干机放到书架位置<br/>
        </div>
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
      xiyijiAlignleft: false // 阳台洗衣机放哪边
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
    },
    // switchAlign() {
    //   console.log(11)
    //   this.xiyijiAlignleft = !this.xiyijiAlignleft
    // }
  }
};
</script>

<style lang="less" scoped>
@import './style/common.less';
@import './app.less';


</style>
