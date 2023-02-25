<script setup>
// 为暗黑模式启用支持
import {useDark, useToggle} from '@vueuse/core'
import {ref} from 'vue'

const dark = ref(
    window.localStorage.getItem('vueuse-color-scheme') === 'dark'
)
const isDark = useDark()
const toggleDark = useToggle(isDark)
const changeTheme = () => {
  dark.value = !dark.value
  toggleDark()
}

const getGitHubLogoUrl = () => {
  return new URL('./assets/img/GitHub.svg', import.meta.url).href
}

const myPhoto = ref(new URL('./assets/img/myPhoto.jpg', import.meta.url).href)

// 引入图标
import {
  GithubOutlined,
  LinkedinOutlined,
  WeiboCircleOutlined
} from '@ant-design/icons-vue'

const goToPage = (url) => {
  window.open(url)
}

const prizes = ref([
  {
    name: '优秀大学生',
    time: '2021.11',
    level: '校级'
  },
  {
    name: '二等奖学金',
    time: '2021.11',
    level: '校级'
  }
])
</script>

<template>
  <div class="common-layout">
    <el-container>
      <el-header>
        <div class="l-content">
          <h1>我的个人简介</h1>
        </div>
        <div class="flex-grow"></div>
        <div class="r-content">
          <el-button v-if="!dark" @click="changeTheme" style="background:#409EFF; color: white">
            <el-icon><Sunny/></el-icon>
            <span>明亮模式</span>
          </el-button>
          <el-button v-else @click="changeTheme" style="background: #303133;color: white">
            <el-icon><Moon/></el-icon>
            <span>暗黑模式</span>
          </el-button>
        </div>
      </el-header>
      <el-container class="home-container">
        <el-aside :width="'30%'">
          <el-card class="left-card">
            <div>
              <img :src="myPhoto" alt="LOGO" class="avatar">
            </div>
            <el-divider />
            <div>
              <h3>王旻安</h3>
              <ul style="text-align: left;">
                <li>
                  <el-icon><Memo /></el-icon>
                  学历: 本科
                </li>
                <li>
                  <el-icon><Calendar /></el-icon>
                  年龄: 21
                </li>
                <li>
                  <el-icon><Location /></el-icon>
                  政治面貌: 共青团员
                </li>
              </ul>
              <img style="height: 180px; width: 100%" src="https://github-readme-stats.vercel.app/api?username=WangMinan&show_icons=true" alt="我的GitHubStatus" />
            </div>
            <el-divider />
            <div>
              <b>我的技术栈</b>
              <p></p>
              <el-row>
                <el-col :span="4">前端:</el-col>
                <el-col :span="20">
                  <div style=" display: flex; justify-content: space-between">
                    <img
                      src="https://img.shields.io/badge/Vue%203%2F2-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="Vue3/2"
                    />
                    <img
                      src="https://img.shields.io/badge/ElementPlus-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="ElementPlus"
                    />
                    <img
                      src="https://img.shields.io/badge/Vite-%E4%BA%86%E8%A7%A3-yellow"
                      alt="Vite"
                    />
                  </div>
                </el-col>
              </el-row>
              <el-row>
                <el-col :span="4">后端:</el-col>
                <el-col :span="20">
                  <div style=" display: flex; justify-content: space-between">
                    <img
                      src="https://img.shields.io/badge/Java-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="Java"
                    />
                    <img
                      src="https://img.shields.io/badge/SpringBoot-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="SpringBoot"
                    />
                    <img
                      src="https://img.shields.io/badge/MyBatisPlus-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="MyBatisPlus"
                    />
                  </div>
                  <div style=" display: flex; justify-content: space-between; margin-top: 1%">
                    <img
                      src="https://img.shields.io/badge/SpringCloud-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="SpringCloud"
                    />
                    <img
                      src="https://img.shields.io/badge/MySQL-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="MySQL"
                    />
                    <img
                      src="https://img.shields.io/badge/Redis-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="Redis"
                    />
                  </div>
                  <div style=" display: flex; justify-content: space-between; margin-top: 1%">
                    <img
                      src="https://img.shields.io/badge/ElasticSearch-%E4%BA%86%E8%A7%A3-yellow"
                      alt="ElasticSearch"
                    />
                    <img
                        src="https://img.shields.io/badge/Nacos-%E4%BA%86%E8%A7%A3-yellow"
                        alt="Nacos"
                    />
                    <img
                        src="https://img.shields.io/badge/RabbitMQ-%E4%BA%86%E8%A7%A3-yellow"
                        alt="RabbitMQ"
                    />
                  </div>
                </el-col>
              </el-row>
              <el-row style="margin-top: 1%">
                <el-col :span="4">服务器:</el-col>
                <el-col :span="20">
                  <div style=" display: flex; justify-content: space-between">
                    <img
                      src="https://img.shields.io/badge/CentOS/AlmaLinux-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="CentOS/AlmaLinux"
                    />
                    <img
                      src="https://img.shields.io/badge/Nginx-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="Nginx"
                    />
                    <img
                        src="https://img.shields.io/badge/Docker-%E4%BA%86%E8%A7%A3-yellow"
                        alt="Docker"
                    />
                  </div>
                  <div style=" display: flex; justify-content: space-between; margin-top: 1%">
                    <img
                      src="https://img.shields.io/badge/GitHub Actions-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="GitHubActions"
                    />
                    <img
                      src="https://img.shields.io/badge/%E9%98%BF%E9%87%8C%E4%BA%91ECS%2FSWAS-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="阿里云ECS/SWAS"
                    />
                  </div>
                  <div style=" display: flex; justify-content: space-between; margin-top: 1%">
                    <img
                      src="https://img.shields.io/badge/%E9%98%BF%E9%87%8C%E4%BA%91OSS-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="阿里云OSS"
                    />
                    <img
                      src="https://img.shields.io/badge/%E9%98%BF%E9%87%8C%E4%BA%91DNS-%E7%86%9F%E7%BB%83-brightgreen"
                      alt="阿里云DNS"
                    />
                    <img
                      src="https://img.shields.io/badge/%E9%98%BF%E9%87%8C%E4%BA%91%E7%9F%AD%E4%BF%A1-%E7%86%9F%E7%BB%83-success"
                      alt="阿里云短信"
                    />
                  </div>
                </el-col>
              </el-row>
            </div>
            <el-divider />
            <div>
              <b>点击下方链接联系我</b>
            </div>
            <ul style="text-align: left;">
              <li>
                <el-icon><Box /></el-icon>
                邮箱:
                <a
                    v-if="dark === false"
                    href="mailto:wangminan0811@hotmail.com"
                    style="text-decoration: none; color: black"
                >
                  wangminan0811@hotmail.com
                </a>
                <a
                    v-else
                    href="mailto:wangminan0811@hotmail.com"
                    style="text-decoration: none; color: white"
                >
                  wangminan0811@hotmail.com
                </a>
              </li>
              <li>
                <el-icon><Phone /></el-icon>
                电话:
                <a
                    v-if="dark === false"
                    href="tel:13777864458"
                    style="text-decoration: none; color: black"
                >
                  13777864458
                </a>
                <a
                    v-else
                    href="tel:13777864458"
                    style="text-decoration: none; color: white"
                >
                  13777864458
                </a>
              </li>
            </ul>
            <el-divider />
            <div>
              <b>我的个人主页</b>
              <p></p>
              <el-row :gutter="5">
                <el-col :span="6">
                  <el-tooltip content="我的GitHub主页" placement="bottom" effect="light">
                    <el-button :size="'large'" type="primary" @click="goToPage('https://github.com/WangMinan')">
                      <github-outlined />
                    </el-button>
                  </el-tooltip>
                </el-col>
                <el-col :span="6">
                  <el-tooltip content="我的领英主页" placement="bottom" effect="light">
                    <el-button :size="'large'" type="success" @click="goToPage('https://github.com/https://www.linkedin.com/in/%E6%97%BB%E5%AE%89-%E7%8E%8B-20b2a1223/')">
                      <linkedin-outlined />
                    </el-button>
                  </el-tooltip>
                </el-col>
                <el-col :span="6">
                  <el-tooltip content="我的微博主页" placement="bottom" effect="light">
                    <el-button :size="'large'" type="default" @click="goToPage('https://www.weibo.com/u/7527520507')">
                      <weibo-circle-outlined />
                    </el-button>
                  </el-tooltip>
                </el-col>
                <el-col :span="6">
                  <el-tooltip content="我的网页状态监控看板" placement="bottom" effect="light">
                    <el-button :size="'large'" type="info" @click="goToPage('https://status.wangminan.me/status/main-status')">
                      <el-icon><DataAnalysis /></el-icon>
                    </el-button>
                  </el-tooltip>
                </el-col>
              </el-row>
            </div>
          </el-card>
        </el-aside>
        <el-divider
          direction="vertical"
          style="height: 70vmax; margin-top: 0.5%; margin-bottom: 0.5%"
        />
        <el-main>
          <el-card class="right-card">
            <div>
              <h1>教育背景</h1>
              <el-divider border-style="dashed"/>
              <el-row :gutter="15">
                <el-col :span="8">学校: 西北工业大学</el-col>
                <el-col :span="8">专业: 软件工程</el-col>
                <el-col :span="8">入学时间: 2020.9-2024.7(预计)</el-col>
              </el-row>
              <el-row :gutter="15">
                <el-col :span="8">绩点: 3.596/4.1</el-col>
                <el-col :span="8">专业排名: 21/290+ 年级前10%</el-col>
                <el-col :span="8"></el-col>
              </el-row>
              <el-row :gutter="15">
                <el-col :span="3">
                  主修课程:
                </el-col>
                <el-col :span="21">
                  <el-row>基础课程: 数据结构 | 计算机网络 | 计算机操作系统 | 计算组成原理 | 数据库系统 | 软件需求工程</el-row>
                  <el-row>专业课程: 软件测试 | Web应用系统开发技术与实践 | 互联网系统开发方向前沿</el-row>
                  <el-row>实践课程: 基于开源和群智的软件工程实践 | 软件开发基础能力训练 | 软件项目组织与管理</el-row>
                </el-col>
              </el-row>
            </div>
            <el-divider>
              <el-icon><star-filled /></el-icon>
            </el-divider>
            <div>
              <h1>荣誉与奖学金</h1>
              <el-divider border-style="dashed" />
              <el-table :data="prizes">
                <el-table-column :label="'荣誉名称'" :prop="'name'"></el-table-column>
                <el-table-column :label="'获得时间'" :prop="'time'"></el-table-column>
                <el-table-column :label="'级别'" :prop="'level'"></el-table-column>
              </el-table>
            </div>
            <el-divider>
              <el-icon><star-filled /></el-icon>
            </el-divider>
            <div>
              <h1>证明与证书</h1>
              <el-divider border-style="dashed" />
              <el-row>
                英语: 大学英语四级 646; 大学英语六级 610
              </el-row>
              <el-row>
                其他: 驾照C1
              </el-row>
            </div>
            <el-divider>
              <el-icon><star-filled /></el-icon>
            </el-divider>
            <div>
              <h1>项目与实习经历</h1>
              <el-divider border-style="dashed" />
              <el-row :gutter="15">
                <el-col :span="11">
                  <p>项目名称: <b>基于心理诱导的监所警员心理保障与管理系统</b></p>
                  <p>
                    项目介绍: 本项目为<b>省级立项大创项目</b>。通过收集并分析监警心理健康状态，对监警的心理状况和监狱的环境进行评估。
                  </p>
                  <p>
                    项目职责: 项目前端开发，前端部署
                  </p>
                  <p>
                    项目技术栈: Vue3.2 + Vite + ElementPlus
                  </p>
                  <a href="https://github.com/WangMinan/management-client">
                    <img
                      :src="'https://github-readme-stats.vercel.app/api/pin/?username=WangMinan&repo=management-client'"
                      :alt="'基于心理诱导的监所警员心理保障与管理系统'"
                    />
                  </a>
                </el-col>
                <el-divider border-style="dashed" direction="vertical" style="height: 23vmax" />
                <el-col :span="11">
                  <p>项目名称: <b>西安各商圈餐饮分析系统</b></p>
                  <p>
                    项目介绍: 本项目为<b>四川华迪实习</b>期间完成项目。根据各类网页的公开数据获取西安各商圈的餐饮行业的流量信息，通过分析展现在数据中台上，供访问用户进行检索。
                  </p>
                  <p>
                    项目职责: 项目后端开发，项目整体部署
                  </p>
                  <p>
                    项目技术栈: SpringBoot + MybatisPlus + ElasticSearch
                  </p>
                  <a href="https://github.com/WangMinan/bigdata_practice">
                    <img
                      :src="'https://github-readme-stats.vercel.app/api/pin/?username=WangMinan&repo=bigdata_practice'"
                      :alt="'西安各商圈餐饮分析系统'"
                    />
                  </a>
                </el-col>
              </el-row>
              <el-divider border-style="dashed" />
              <el-row :gutter="15">
                <el-col :span="11">
                  <p>项目名称: <b>书影音评价系统</b></p>
                  <p>
                    项目介绍: 本项目为<b>Web应用系统开发与实践</b>课程设计。是一个简单的书影音评价系统，用户可以在系统中对书影音进行评价，也可以查看其他用户的评价。
                  </p>
                  <p>
                    项目职责: 项目前端、后端开发，项目整体部署
                  </p>
                  <p>
                    项目技术栈: Vue2 + ElementUI + SpringBoot + Redis + MybatisPlus
                  </p>
                  <a href="https://github.com/WangMinan/OnlineBookMovieFilmRatingSystem">
                    <img
                        :src="'https://github-readme-stats.vercel.app/api/pin/?username=WangMinan&repo=OnlineBookMovieFilmRatingSystem'"
                        :alt="'书影音评价系统'"
                    />
                  </a>
                </el-col>
                <el-divider border-style="dashed" direction="vertical" style="height: 23vmax" />
                <el-col :span="11">
                  <p>项目名称: <b>新蜂商城(基于开源的二次开发)</b></p>
                  <p>
                    项目介绍: 本软件是基于开源与群智的软件工程实践课程的课程设计。是一个基于SpringBoot的电商系统，我修复了代码的异味，为该项目引入了<b>支付宝支付</b>功能。
                  </p>
                  <p>
                    项目职责: 项目后端开发，项目整体部署
                  </p>
                  <p>
                    项目技术栈: SpringBoot + MybatisPlus + Alipay-SDK
                  </p>
                  <a href="https://github.com/WangMinan/newbee-mall-api">
                    <img
                      :src="'https://github-readme-stats.vercel.app/api/pin/?username=WangMinan&repo=newbee-mall-api'"
                      :alt="'新蜂商城'"
                    />
                  </a>
                </el-col>
              </el-row>
            </div>
          </el-card>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<style lang="less">
.common-layout{
  height: 100%;
  width: 100%;
}
.home-container{
  height: 100%;
  width: 100%;
}
.el-header{
  width: 100%;
  padding: 0 10px;
  background: #79BBFF;
  display: flex;
  align-items: center;
  .l-content{
    color: white;
    margin-left: 1%;
  }
  .flex-grow {
    flex-grow: 1;
  }
  .r-content{
    padding: 0 10px;
    .user-icon{
      width: 30px;
      height: 30px;
      border-radius: 50%;
      // 设置底色为白色
      background: white;
    }
  }
}
.el-aside{
  .left-card{
    width: 90%;
    margin-top: 4.5%;
    // 左右居中
    margin-left: 5%;
    display: flex;
    justify-content: center;
    text-align: center;
    align-items: center;
    .avatar{
      border-radius: 50%;
      width: 60px;
      height: 60px;
      // 正中放大
      transform: scale(1.2);
    }
  }
}
.right-card{
  .el-row{
    margin-top: 0.5%;
  }
}
</style>
