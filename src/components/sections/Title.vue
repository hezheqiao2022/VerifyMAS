<script lang="ts" setup>
import { ElIcon } from 'element-plus'
import { Notebook } from '@element-plus/icons-vue'

// Logo 地址，没有则置为 ''
const logo = 'resources/logo_full.png'

// 标题
const title = ''

// 标题颜色
const title_color = '#000000'

// 标题补充
const title_supp =
  'VerifyMAS: Hypothesis Verification for Failure Attribution in LLM Multi-Agent Systems'

// 标题补充颜色
const title_supp_color = '#000000'

// 会议名称，没有则置为 ''
const conference = 'NeurIPS 2026'

// 按钮颜色
const btn_color = '#444444'

// 作者清单
const authors = [
  {
    name: 'Hezhe Qiao',
    icon: '',
    homepage: 'https://hezheqiao2022.github.io/',
    address_flag: '1',
  },
  {
    name: 'Hanghang Tong',
    icon: '',
    homepage: 'http://tonghanghang.org/',
    address_flag: '2',
  },
  {
    name: 'Ee-Peng Lim',
    icon: '',
    homepage: 'https://faculty.smu.edu.sg/profile/lim-ee-peng-616',
    address_flag: '1',
  },
  {
    name: 'Bing Liu',
    icon: '',
    homepage: 'https://www.cs.uic.edu/~liub/',
    address_flag: '3',
  },
  {
    name: 'Guansong Pang',
    icon: '',
    homepage: 'https://sites.google.com/site/gspangsite/home',
    address_flag: '1,†',
  },
]

// 地址清单
const addresses = [
  {
    address_flag: '1',
    name: 'Singapore Management University',
    icon: 'resources/smu_logo.png',
    homepage: '',
  },
  {
    address_flag: '2',
    name: 'University of Illinois Urbana-Champaign',
    icon: 'resources/uiuc_logo.png',
    homepage: '',
  },
  {
    address_flag: '3',
    name: 'University of Illinois Chicago',
    icon: 'resources/uic_logo.png',
    homepage: '',
  },
]

// 共一和通讯提示
const con_and_corresponding_author = ''

// 最新消息
const news = ''

// 强调内容
const emphases: string[] = []

// 引导资料链接
const buttons = [
  {
    disabled: false,
    name: 'Paper',
    link: 'https://arxiv.org/abs/2605.17467',
    iconImg: 'resources/arxiv_logo.svg',
  },
  {
    disabled: false,
    name: 'Code',
    link: 'https://github.com/mala-lab/VerifyMAS',
    iconImg: 'resources/github_logo.svg',
  },
  {
    disabled: false,
    name: 'Dataset',
    link: '',
    iconImg: 'resources/huggingface_logo.png',
  },
  {
    disabled: false,
    name: 'BibTeX',
    link: '#bibtex',
    component: Notebook,
  },
]
</script>

<template>
  <div>
    <!-- 最新消息提示 -->
    <el-row v-if="news" justify="center">
      <el-col :span="24">
        <el-alert :title="news" type="success" />
      </el-col>
    </el-row>

    <!-- 文章 Logo -->
    <el-row v-if="logo" justify="center">
      <el-image :src="logo" class="logo" fit="contain" />
    </el-row>

    <!-- 文章标题 -->
    <el-row justify="center">
      <el-col :span="20">
        <h1 class="paper-title">
          <span v-if="title" :style="{ color: title_color }">
            {{ title }}
          </span>
          <span v-if="title_supp" :style="{ color: title_supp_color }">
            {{ title_supp }}
          </span>
        </h1>
      </el-col>
    </el-row>

    <!-- 会议标识 -->
    <el-row
      v-if="conference"
      justify="center"
      class="conference-row"
    >
      <span class="conference-badge">
        {{ conference }}
      </span>
    </el-row>

    <!-- 作者名单 -->
    <el-row justify="center">
      <a
        v-for="author in authors"
        :key="author.name"
        :href="author.homepage"
      >
        <el-button class="title-button" type="primary" text>
          <el-avatar
            v-if="author.icon"
            :size="40"
            :src="author.icon"
          />
          <span class="author">
            {{ author.name }}<sup
              v-if="author.address_flag"
              class="name_sup"
            >{{ author.address_flag }}</sup>
          </span>
        </el-button>
      </a>
    </el-row>

    <!-- 地址名单 -->
    <el-row justify="center">
      <a
        v-for="address in addresses"
        :key="address.address_flag"
        :href="address.homepage"
      >
        <el-button class="title-button" type="primary" text>
          <img
            v-if="address.icon"
            class="address-logo"
            :src="address.icon"
            :alt="address.name"
          />
          <span class="address">
            <sup
              v-if="address.address_flag"
              class="address_sup"
            >{{ address.address_flag }}</sup>{{ address.name }}
          </span>
        </el-button>
      </a>
    </el-row>

    <!-- 共一和通讯提示 -->
    <el-row justify="center" class="con-cor">
      {{ con_and_corresponding_author }}
    </el-row>

    <!-- 强调内容 -->
    <el-row
      v-for="(emphasis, i) in emphases"
      :key="i"
      justify="center"
      class="emphasis"
    >
      {{ emphasis }}
    </el-row>

    <!-- 引导资料按钮 -->
    <el-row justify="center" style="margin-bottom: 20px">
      <el-col :span="20">
        <el-row justify="center">
          <a
            v-for="button in buttons"
            :key="button.name"
            :href="button.link"
          >
            <el-button
              class="guidance-button"
              size="default"
              :color="btn_color"
              :disabled="button.disabled"
              round
            >
              <el-icon :size="18">
                <component
                  v-if="button.component"
                  :is="button.component"
                />
                <img
                  v-else-if="button.iconImg"
                  :src="button.iconImg"
                  :alt="button.name"
                  class="btn-icon-img"
                />
              </el-icon>
              <span class="btn-text">
                {{ button.name }}
              </span>
            </el-button>
          </a>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
/* 文章标题 */
.paper-title {
  font-family: "MyFont", Verdana, sans-serif;
  letter-spacing: 1px;
  font-size: 38px;
  line-height: 1.25;
  margin: 8px 0 14px;
  text-align: center;
}

/* 会议标识 */
.conference-row {
  margin-bottom: 16px;
}

.conference-badge {
  display: inline-block;
  padding: 7px 22px;
  border: 1px solid #ddd6fe;
  border-radius: 999px;
  background: #f5f3ff;
  color: #6d28d9;
  font-family: Arial, sans-serif;
  font-size: 20px;
  font-weight: 700;
  line-height: 1.4;
  letter-spacing: 0.6px;
}

/* 姓名和地址按钮 */
.title-button {
  margin: 10px 3px;
}

/* 姓名和地址按钮悬浮 */
.title-button:hover {
  margin: 10px 8px;
}

/* 引导资料按钮 */
.guidance-button {
  margin: 8px 5px;
  box-shadow: #d8d8d8 1px 1px 1px 1px;
}

/* 姓名 */
.author {
  font-size: 18px;
  margin-left: 3px;
}

/* 姓名上标 */
.name_sup {
  color: #606266;
  margin-left: 3px;
}

/* 地址 */
.address {
  font-size: 18px;
}

/* 地址上标 */
.address_sup {
  color: #606266;
  margin-right: 1px;
}

/* 作者头像 */
.el-avatar {
  margin-right: 6px;
  box-shadow: #b7b7b7 0 0 3px 1px;
}

/* 机构 Logo */
.address-logo {
  height: 36px;
  width: auto;
  max-width: 50px;
  object-fit: contain;
  margin-right: 8px;
  vertical-align: middle;
}

/* 共一和通讯提示 */
.con-cor {
  font-family: Arial, sans-serif;
  font-size: 14px;
  margin: 18px 0;
  text-align: center;
}

/* 强调信息 */
.emphasis {
  color: chocolate;
  font-weight: bold;
  margin: 8px;
  font-size: 22px;
  text-align: center;
}

/* 引导按钮文字 */
.btn-text {
  font-size: 18px;
  color: #ffffff;
}

/* 引导按钮图片图标 */
.btn-icon-img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

/* 最新消息提示 */
.el-alert {
  margin: 10px 0 0;
}

.el-alert:first-child {
  margin: 0;
}

/* 文章 Logo */
.logo {
  width: 520px;
  max-width: 90%;
  height: auto;
  margin-top: 40px;
}

/* 手机端链接样式 */
a:-webkit-any-link {
  text-decoration: none;
}

/* 链接悬浮样式 */
a:hover {
  color: inherit;
  border-bottom: none;
}

/* 通用链接样式 */
a {
  text-decoration: none;
  color: inherit;
}

/* 手机端会议标识 */
@media (max-width: 600px) {
  .conference-badge {
    padding: 6px 18px;
    font-size: 18px;
  }
}
</style>