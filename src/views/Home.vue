
<template>
  <div class="home">
    <imooc-loading v-if="loading">
      <div class="loading-text">
        数据大屏加载中...
      </div>
    </imooc-loading>
    <wu-container v-else :options="{width:3840,height:2160}">
      <div class="header">
        <top-header />
      </div>
      <div class="separator" />
      <div class="center">
        <div class="left">
          <div class="left1">
            <total-user :today-user="todayUser" :growth-last-day="growthLastDay" :growth-last-month="growthLastMonth" />
          </div>
          <div class="left2">
            <average-age :data="ageData" :avgAge="averageAge"></average-age>
          </div>
          <div class="left3">
            <total-device :data="deviceData" />
          </div>
          <div class="left4">
            <total-gender :data="genderData" />
          </div>
          <div class="left5">
            <total-rider :data="riderData" />
          </div>
          <div class="left6">
            <hot-category :data="hotCategoryData" />
          </div>
        </div>
        <div class="right">
          <div class="right-top1">
            <center-header :data="headerData" />
          </div>
          <div class="right-top2">right-top2</div>
          <div class="right-bottom">
            <div class="right-left">
              <div class="right-left1">right-left1</div>
              <div class="right-left2">right-left2</div>
              <div class="right-left3">right-left3</div>
              <div class="right-left4">right-left4</div>
            </div>
            <div class="right-right">
              <div class="right-right1">right-right1</div>
              <div class="right-right2">right-right2</div>
            </div>
          </div>
        </div>
      </div>
    </wu-container>
  </div>
</template>

<script>
/* eslint-disable no-unused-vars */
import TopHeader from '@/components/TopHeader'
import TotalUser from '@/components/TotalUser'
import TotalGender from '@/components/TotalGender'
import TotalRider from '@/components/TotalRider'
import AverageAge from '@/components/AverageAge'
import HotCategory from '@/components/HotCategory'
import CenterHeader from '@/components/CenterHeader'
import { ref } from 'vue'
import useScreenData from '@/hooks/useScreenData'
import TotalDevice from '@/components/TotalDevice'
// @ is an alias to /src
export default {
  name: 'Home',
  components: {
    TopHeader,
    TotalUser,
    AverageAge,
    TotalDevice,
    TotalGender,
    TotalRider,
    HotCategory,
    CenterHeader
  },
  setup() {
    const loading = ref(false)
    return {
      loading,
      ...useScreenData()
    }
  }
}
</script>

<style lang="scss" scoped>
.home {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  background: rgb(29, 29, 29);
  color: #fff;
  font-size: 48px;
  #wu-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    .header {
      width: 100%;
      height: 167px;
    }
    .separator {
      width: 100%;
      height: 10px;
      background: rgb(92, 88, 89);
    }
    .center {
      width: 100%;
      flex: 1;
      display: flex;
      .left {
        flex: 0 0 860px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        width: 860px;
        height: 100%;
        padding-bottom: 20;
        box-sizing: border-box;
        background: rgb(60, 61, 64);
        .left1 {
          height: 300px;
        }
        .left2 {
          height: 320px;
        }
        .left3 {
          height: 280px;
        }
        .left4 {
          height: 230px;
        }
        .left5 {
          height: 360px;
        }
        .left6 {
          height: 360px;
        }
      }
      .right {
        flex: 1;
        display: flex;
        flex-direction: column;
        margin-left: 10px;
        .right-top1 {
          width: 100%;
          height: 206px;
        }
        .right-top2 {
          width: 100%;
          height: 48px;
        }
        .right-bottom {
          flex: 1;
          display: flex;
          padding-bottom: 20px;
          .right-left {
            flex: 0 0 1917px;
            display: flex;
            justify-content: space-between;
            flex-direction: column;
            width: 1917px;
            .right-left1 {
              height: 999px;
            }
            .right-left2 {
              height: 80px;
            }
            .right-left3 {
              height: 350px;
            }
            .right-left4 {
              height: 220px;
            }
          }
          .right-right {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            margin-left: 10px;
            .right-right1 {
              width: 100%;
              height: 999px;
            }
            .right-right2 {
              flex: 1;
              margin-top: 20px;
              width: 100%;
            }
          }
        }
      }
    }
  }
}
.loading-text {
  font-size: 20px;
  margin-top: 10px;
}
</style>
