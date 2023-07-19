<template>
  <div class="mossai">
    <a-layout class="layout-demo">
      <a-layout-sider hide-trigger collapsible :collapsed="collapsed" style="width: 256px;">
        <div class="logo">
          <img src="../assets/images/logo.png">
        </div>
        <a-menu :defaultOpenKeys="['1']" :defaultSelectedKeys="['0_3']" :style="{ width: '256px' }"
          @menuItemClick="onClickMenuItem">
          <a-menu-item key="0_1">
            <IconHome />
            主页
          </a-menu-item>
          <a-menu-item key="0_2">
            <IconCalendar />
            智能对话
          </a-menu-item>
          <a-menu-item key="0_3">
            <IconCalendar />
            智能绘画
          </a-menu-item>
          <!-- <a-sub-menu key="1">
            <template #title>
              <span>
                <IconCalendar />Navigation 1
              </span>
            </template>
            <a-menu-item key="1_1">Menu 1</a-menu-item>
            <a-menu-item key="1_2">Menu 2</a-menu-item>
            <a-sub-menu key="2" title="Navigation 2">
              <a-menu-item key="2_1">Menu 1</a-menu-item>
              <a-menu-item key="2_2">Menu 2</a-menu-item>
            </a-sub-menu>
            <a-sub-menu key="3" title="Navigation 3">
              <a-menu-item key="3_1">Menu 1</a-menu-item>
              <a-menu-item key="3_2">Menu 2</a-menu-item>
              <a-menu-item key="3_3">Menu 3</a-menu-item>
            </a-sub-menu>
          </a-sub-menu>
          <a-sub-menu key="4">
            <template #title>
              <span>
                <IconCalendar />Navigation 4
              </span>
            </template>
            <a-menu-item key="4_1">Menu 1</a-menu-item>
            <a-menu-item key="4_2">Menu 2</a-menu-item>
            <a-menu-item key="4_3">Menu 3</a-menu-item>
          </a-sub-menu> -->
        </a-menu>



        <div class="mossai_myinformation_bos">
          <div class="mossai_myinformation_bos_left">
            <img style="width: 40px;height: 40px;border-radius: 50%;" src="../assets/images/user.png" alt="" srcset="">
          </div>
          <div class="mossai_myinformation_bos_main" style="margin-right: 40px;">
            <p style="font-size: 16px; color: #11142D; font-weight: 600;">莫斯用户</p>
            <p style="font-size: 14px; color: #808191; font-weight: 600;">打工人</p>
          </div>
          <div class="mossai_myinformation_bos_right">
            <img style="width: 24px;height: 24px;" src="../assets/images/list.png" alt="" srcset="">
          </div>
        </div>

      </a-layout-sider>

      <a-layout style="display: flex;">
        <!-- <a-layout-header style="padding-left: 20px;">
          <a-button shape="round" @click="onCollapse">
            <IconCaretRight v-if="collapsed" />
            <IconCaretLeft v-else />
          </a-button>
        </a-layout-header> -->
        <a-layout style="padding: 0 24px;margin: 47px 0 0 34px;">

          <!-- 欢迎标题 -->
          <div class="mossai_toptext" style="margin-bottom: 30px;">
            <p style="font-size: 32px;">Hi 打工人,</p>
            <p style="font-size: 52px;">今天要点什么？</p>
          </div>
          <!-- 轮播图 -->
          <div class="mossai_imgs">
            <a-carousel :indicator-type="indicatorType" :indicator-position="indicatorPosition" show-arrow="never" :style="{
              width: '628px',
              height: '425px',
            }">
              <a-carousel-item v-for="image in images">
                <img :src="image" :style="{
                  width: '100%',
                }" />
              </a-carousel-item>
            </a-carousel>
          </div>

          <br>
          <!-- 热门工具 -->
          <div class="mossai_popularTools">
            <p style="font-size: 36px; font-weight: 800; color: #11142D; margin-bottom: 30px;">热门工具</p>
            <div class="mossai_popularTools_item">
              <div class="mossai_popularTools_item_box_one">
                <p style="font-size: 22px;font-weight: 600;color: #11142D;">模型3.5对话</p>
                <p style="font-size: 12px;color: #808191;">今日对话6666次</p>
                <p style="font-size: 12px;color: #808191;margin-top: 37px;">2333人在使用</p>
                <div class="mossai_popularTools_item_box_one_img">
                  <img style="width: 64px;height: 24px;" src="../assets/images/Group48.png" alt="">
                  <img style="width: 16px;height: 16px;" src="../assets/images/shape-star2.png" alt="" srcset="">
                  <img style="width: 16px;height: 16px;" src="../assets/images/menu-51.png" alt="" srcset="">
                </div>
              </div>
              <div class="mossai_popularTools_item_box_one">
                <p style="font-size: 22px;font-weight: 600;color: #11142D;">模型4.0对话</p>
                <p style="font-size: 12px;color: #808191;">今日对话3333次</p>
                <p style="font-size: 12px;color: #808191;margin-top: 37px;">333人在使用</p>
                <div class="mossai_popularTools_item_box_one_img">
                  <img style="width: 64px;height: 24px;" src="../assets/images/Group48(1).png" alt="">
                  <img style="width: 16px;height: 16px;" src="../assets/images/shape-star2.png" alt="" srcset="">
                  <img style="width: 16px;height: 16px;" src="../assets/images/menu-51.png" alt="" srcset="">
                </div>
              </div>
              <div class="mossai_popularTools_item_box_one">
                <p style="font-size: 22px;font-weight: 600;color: #11142D;">高级绘画</p>
                <p style="font-size: 12px;color: #808191;">今日绘画666张</p>
                <p style="font-size: 12px;color: #808191;margin-top: 37px;">66人在使用</p>
                <div class="mossai_popularTools_item_box_one_img">
                  <img style="width: 64px;height: 24px;" src="../assets/images/Group48(2).png" alt="">
                  <img style="width: 16px;height: 16px;" src="../assets/images/shape-star2.png" alt="" srcset="">
                  <img style="width: 16px;height: 16px;" src="../assets/images/menu-51.png" alt="" srcset="">
                </div>
              </div>
              <div class="mossai_popularTools_item_box_one">
                <p style="font-size: 22px;font-weight: 600;color: #11142D;">视频合成</p>
                <p style="font-size: 12px;color: #808191;">今日合成20张</p>
                <p style="font-size: 12px;color: #808191;margin-top: 37px;">20人在使用</p>
                <div class="mossai_popularTools_item_box_one_img">
                  <img style="width: 64px;height: 24px;" src="../assets/images/Group48(1).png" alt="">
                  <img style="width: 16px;height: 16px;" src="../assets/images/shape-star2.png" alt="" srcset="">
                  <img style="width: 16px;height: 16px;" src="../assets/images/menu-51.png" alt="" srcset="">
                </div>
              </div>
            </div>
          </div>


          <!-- <a-breadcrumb :style="{ margin: '16px 0' }">
            <a-breadcrumb-item>Home</a-breadcrumb-item>
            <a-breadcrumb-item>List</a-breadcrumb-item>
            <a-breadcrumb-item>App</a-breadcrumb-item>
          </a-breadcrumb>
          <a-layout-content>Content</a-layout-content>
          <a-layout-footer>Footer</a-layout-footer> -->
        </a-layout>





      </a-layout>




    </a-layout>


    <div class="mossai_right">
      <!-- 欢迎标题 -->
      <div class="mossai_right_toptext"
        style="margin-top: 50px;margin-left: 80px;display: flex; align-items: center;justify-content: space-between;">
        <a-input-search :style="{ width: '250px' }" placeholder="搜索" search-button />
        <img style="width: 60px;height: 60px;margin-right: 50px;" src="../assets/images/icon.png" alt="" srcset="">
      </div>


      <!-- 热门小应用 -->
      <div class="mossai_right_smallApplication">
        <p style="font-size: 22px; color: #11142D;font-weight: 600;margin-left: 80px;">热门小应用</p>
        <div class="mossai_right_smallApplication_list">
          <div class="mossai_right_smallApplication_list_bos">
            <div class="smallApplication_list_bos_left" style="margin: 0 24px 0 24px;">
              <img style="width: 56px;height: 56px;" src="../assets/images/bot.png" alt="" srcset="">
            </div>
            <div class="smallApplication_list_bos_main">
              <p style="font-size: 22px; color: #11142D; font-weight: 600;">智能对话机器人</p>
              <p style="font-size: 18px; color: #808191; font-weight: 600;">无所不能</p>
            </div>
            <div class="smallApplication_list_bos_right" style="position: absolute;right: 10px;">
              <img style="width: 24px;height: 24px;" src="../assets/images/smallright.png" alt="" srcset="">
            </div>
          </div>
          <div class="mossai_right_smallApplication_list_bos">
            <div class="smallApplication_list_bos_left" style="margin: 0 24px 0 24px;">
              <img style="width: 56px;height: 56px;" src="../assets/images/play.png" alt="" srcset="">
            </div>
            <div class="smallApplication_list_bos_main">
              <p style="font-size: 22px; color: #11142D; font-weight: 600;">智能对话机器人</p>
              <p style="font-size: 18px; color: #808191; font-weight: 600;">无所不能</p>
            </div>
            <div class="smallApplication_list_bos_right" style="position: absolute;right: 10px;">
              <img style="width: 24px;height: 24px;" src="../assets/images/smallright.png" alt="" srcset="">
            </div>
          </div>

          <div class="mossai_right_smallApplication_list_bos">
            <div class="smallApplication_list_bos_left" style="margin: 0 24px 0 24px;">
              <img style="width: 56px;height: 56px;" src="../assets/images/midjourney.png" alt="" srcset="">
            </div>
            <div class="smallApplication_list_bos_main">
              <p style="font-size: 22px; color: #11142D; font-weight: 600;">智能对话机器人</p>
              <p style="font-size: 18px; color: #808191; font-weight: 600;">无所不能</p>
            </div>
            <div class="smallApplication_list_bos_right" style="position: absolute;right: 10px;">
              <img style="width: 24px;height: 24px;" src="../assets/images/smallright.png" alt="" srcset="">
            </div>
          </div>

          <div class="mossai_right_smallApplication_list_bos">
            <div class="smallApplication_list_bos_left" style="margin: 0 24px 0 24px;">
              <img style="width: 56px;height: 56px;" src="../assets/images/weixin.png" alt="" srcset="">
            </div>
            <div class="smallApplication_list_bos_main">
              <p style="font-size: 22px; color: #11142D; font-weight: 600;">智能对话机器人</p>
              <p style="font-size: 18px; color: #808191; font-weight: 600;">无所不能</p>
            </div>
            <div class="smallApplication_list_bos_right" style="position: absolute;right: 10px;">
              <img style="width: 24px;height: 24px;" src="../assets/images/smallright.png" alt="" srcset="">
            </div>
          </div>
        </div>
      </div>


      
      <p style="font-size: 22px; color: #11142D;font-weight: 600;margin-left: 80px;margin-top: 40px;">额度仪表</p>
      <div id="main" style="width: 600px; height: 400px;">

      </div>

    </div>
  </div>
</template>
<script>
import { defineComponent, ref,onMounted } from 'vue';
import { Message } from '@arco-design/web-vue';
import * as echarts from 'echarts';
import {
  IconCaretRight,
  IconCaretLeft,
  IconHome,
  IconCalendar,
} from '@arco-design/web-vue/es/icon';



import shufflingFigure from '../assets/images/shufflingFigure.png'

export default defineComponent({
  components: {
    IconCaretRight,
    IconCaretLeft,
    IconHome,
    IconCalendar,
  },
  setup() {
    const collapsed = ref(false);
    const onCollapse = () => {
      collapsed.value = !collapsed.value;
    };

    onMounted(() => {
      initChart();
    });

    function initChart() {
      var chartDom = document.getElementById('main');
      var myChart = echarts.init(chartDom);
      var option;

      const gaugeData = [
        {
          value: 20,
          name: '3.5额度',
          title: {
            offsetCenter: ['-40%', '80%']
          },
          detail: {
            offsetCenter: ['-40%', '95%']
          }
        },
        {
          value: 40,
          name: '4.0额度',
          title: {
            offsetCenter: ['0%', '80%']
          },
          detail: {
            offsetCenter: ['0%', '95%']
          }
        },
        {
          value: 60,
          name: '绘画额度',
          title: {
            offsetCenter: ['40%', '80%']
          },
          detail: {
            offsetCenter: ['40%', '95%']
          }
        }
      ];
      option = {
        series: [
          {
            type: 'gauge',
            anchor: {
              show: true,
              showAbove: true,
              size: 18,
              itemStyle: {
                color: '#FAC858'
              }
            },
            pointer: {
              icon: 'path://M2.9,0.7L2.9,0.7c1.4,0,2.6,1.2,2.6,2.6v115c0,1.4-1.2,2.6-2.6,2.6l0,0c-1.4,0-2.6-1.2-2.6-2.6V3.3C0.3,1.9,1.4,0.7,2.9,0.7z',
              width: 8,
              length: '80%',
              offsetCenter: [0, '8%']
            },
            progress: {
              show: true,
              overlap: true,
              roundCap: true
            },
            axisLine: {
              roundCap: true
            },
            data: gaugeData,
            title: {
              fontSize: 14
            },
            detail: {
              width: 40,
              height: 14,
              fontSize: 14,
              color: '#fff',
              backgroundColor: 'inherit',
              borderRadius: 3,
              formatter: '{value}%'
            }
          }
        ]
      };
      setInterval(function () {
        gaugeData[0].value = +(Math.random() * 100).toFixed(2);
        gaugeData[1].value = +(Math.random() * 100).toFixed(2);
        gaugeData[2].value = +(Math.random() * 100).toFixed(2);
        myChart.setOption({
          series: [
            {
              data: gaugeData
            }
          ]
        });
      }, 2000);

      option && myChart.setOption(option);

    }




    // 轮播图
    const images = ref([
      shufflingFigure,
      'https://p1-arco.byteimg.com/tos-cn-i-uwbnlip3yd/6480dbc69be1b5de95010289787d64f1.png~tplv-uwbnlip3yd-webp.webp',
      'https://p1-arco.byteimg.com/tos-cn-i-uwbnlip3yd/0265a04fddbd77a19602a15d9d55d797.png~tplv-uwbnlip3yd-webp.webp',
    ])

    const indicatorType = ref('dot');
    const indicatorPosition = ref('bottom');


    return {
      collapsed,
      onCollapse,
      onClickMenuItem(key) {
        Message.info({ content: `You select ${key}`, showIcon: true });
      },
      images,
      indicatorType,
      indicatorPosition,
    };
  },
});
</script>
<style scoped>
.mossai {
  width: 100%;
  height: 100vh;
  display: flex;
}


.mossai_right {
  width: 600px;
  background-color: #F5FBFF;
}

::v-deep .arco-menu-vertical .arco-menu-inner {
  padding: 0;
}


::v-deep .arco-menu-item {
  width: 100%;
  height: 56px;
  line-height: 56px;
}


::v-deep .arco-menu-item:hover {
  background-color: none;
}


::v-deep .arco-menu-vertical .arco-menu-item,
.arco-menu-vertical .arco-menu-group-title,
.arco-menu-vertical .arco-menu-pop-header,
.arco-menu-vertical .arco-menu-inline-header {
  margin-bottom: 0;
  line-height: 56px;
}


::v-deep .arco-menu-light .arco-menu-item.arco-menu-selected {
  width: 85%;
  border-top-right-radius: 15px;
  border-bottom-right-radius: 15px;
  background-color: #2F3CED;
  color: #fff;
  font-size: 14px;
  font-weight: 600;
  letter-spacing: 0px;
}

::v-deep .layout-demo[data-v-b4e148ca] .arco-layout-sider-light .logo {
  background-color: #FDFDFD;
}


::v-deep .arco-layout {
  background-color: #f3f4f7;
}



.layout-demo {
  width: 100%;
  height: 100%;
  background: var(--color-fill-2);
  border: 1px solid var(--color-border);
}

.layout-demo :deep(.arco-layout-sider) .logo {
  width: 256px;
  height: 178px;
  background-color: #fff;
  display: flex;
}


.layout-demo :deep(.arco-layout-sider) .logo img {
  width: 108px;
  height: 67px;
  margin: 0 auto;
  margin-top: 49px;
  /* margin-left: 42px; */

}



.layout-demo :deep(.arco-layout-sider-light) .logo {
  background: var(--color-fill-2);
}




.layout-demo :deep(.arco-layout-header) {
  height: 64px;
  line-height: 64px;
  background: var(--color-bg-3);
}

.layout-demo :deep(.arco-layout-footer) {
  height: 48px;
  color: var(--color-text-2);
  font-weight: 400;
  font-size: 14px;
  line-height: 48px;
}

.layout-demo :deep(.arco-layout-content) {
  color: var(--color-text-2);
  font-weight: 400;
  font-size: 14px;
  background: var(--color-bg-3);
}

.layout-demo :deep(.arco-layout-footer),
.layout-demo :deep(.arco-layout-content) {
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: var(--color-white);
  font-size: 16px;
  font-stretch: condensed;
  text-align: center;
}




/* 热门工具 */
.mossai_popularTools {
  margin-top: 42px;
}


.mossai_popularTools_item {
  width: 90%;
  display: flex;
  justify-content: space-between;
}

.mossai_popularTools_item_box_one {
  width: 190px;
  height: 187px;
  background: #FFFFFF;
  border-radius: 24px;
  padding: 24px 14px 14px 24px;
}

.mossai_popularTools_item_box_one_img {

  display: flex;
  justify-content: space-between;
}

.mossai_popularTools_item_box_one_img:nth-child(1) {
  width: 64px;
  height: 24px;
}

.mossai_popularTools_item_box_one_img:nth-child(2) {
  width: 16px;
  height: 16px;
}

.mossai_popularTools_item_box_one_img:nth-child(3) {
  width: 16px;
  height: 16px;
}



.mossai_right_smallApplication {
  margin-top: 84px;
}


.mossai_right_smallApplication_list {
  width: 100%;
  margin-top: 22px;
}

.mossai_right_smallApplication_list_bos {
  width: 444px;
  height: 84px;
  border-radius: 10px;
  background-color: #fff;
  margin: 0 auto;
  margin-bottom: 15px;
  display: flex;
  align-items: center;
  position: relative;
}



.mossai_myinformation_bos {
  width: 256px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  position: fixed;
  bottom: 15px;
}
</style>
