<template>
  <div class="second-screen" id="second-screen">
    <div class="resume">
      <div class="resume-header">
        <div class="avatar-box">
          <img class="avatar" src="@/assets/images/avatar_anderson.png" />
          <span></span><span></span><span></span>
        </div>
      </div>

      <t-row style="width:100%;">
        <t-col :md="6">
          <!-- <div style="width:100%;">
            <img class="avatar" src="@/assets/images/avatar.png" />
          </div> -->
          <div class="resume_about">
            <span class="label">姓名: </span
            ><span style="font-size:26px"
              >{{ about.name
              }}<span style="font-weight:700;padding-left:1em;"
                >{{ about.name_en }}
              </span></span
            >
            <span class="label">学历: </span><span>大专</span>
            <span class="label">微信: </span><span>{{ about.wechat }}</span>
            <span class="label">电话: </span><span>{{ about.mobile }}</span>
            <span class="label">邮箱: </span><span>{{ about.email }}</span>
            <span class="label">钉钉: </span><span>{{ about.dingtalk }}</span>
          </div>
          <div class="QRcode">
            <img src="@/assets/images/QRcode.jpg" alt="" />
          </div>
        </t-col>
        <t-col :md="6">
          <div class="dev_experience">
            <ul class="exp_parent">
              <li
                class="exp_parent-item"
                v-for="(items, i) in experince"
                :key="i"
              >
                <ul class="exp_children">
                  <li class="exp_children-item describe">
                    {{ items.describe }}
                  </li>
                  <li
                    class="exp_children-item"
                    v-for="(item, index) in items.details"
                    :key="index"
                  >
                    <span>{{ index + 1 }}.</span>
                    {{ item }}
                  </li>
                </ul>
              </li>
            </ul>
          </div>
        </t-col>
      </t-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'secondScreen',
  data: () => ({
    about: {
      name: '江佩杰',
      name_en: 'Anderson',
      wechat: 'Anderson-Kong',
      mobile: '18927912786',
      email: 'AndersonKong@hotmail.com',
      dingtalk: 'AndersonKong@hotmail.com'
    },
    experince: [
      {
        describe:
          '使用Vue-Cli脚手架开发基于CMS(Content Management System)的前端项目,熟练使用VueRoute,VueX，Axios等技术',
        details: [
          '媒体查询，页面自适应，栅格布局，Flex布局，Grid布局',
          '页面懒加载，动态加载组件',
          '异步请求，Axios配置',
          'Vuex的持久化状态管理',
          '支持移动端触摸的全屏轮播图',
          'Echart实现数据可视化',
          '基于Canvas生成的图片验证码'
        ]
      },
      {
        describe:
          '使用JQuery编写页面交互效果以及GSAP动画插件制作的页面动态展示效果',
        details: ['Ajax请求', 'DOM操作', '动画加载效果']
      },
      {
        describe:
          '在校期间参与了WEB仿站的团队项目，制作了仿新浪微博PC端和移动端的网页应用，个人分工部分参与了Laravel（PHP框架）以及Vue的使用及开发',
        details: [
          '路由鉴权，页面访问和按钮的RCBA(role-based access control)',
          'MVC，后端路由，表单验证，数据迁移，数据填充，登录验证',
          '数据填充，登录验证MySQL CURD'
        ]
      },
      {
        describe: '使用MasterGO等产品设计软件，参与了页面以及交互设计',
        details: ['页面布局，栅格系统']
      }
    ]
  }),
  methods: {
    showData: () => {
      const { about } = data.data
      console.log(about)
    }
  },
  mounted () {}
}
</script>
<style lang="less" scope>
@fontSize: 18px;
@color: #2f9e44;
@font-color: #505050;
@font-low-color: #bbbec0;

.second-screen {
  width: 100vw;
  // height: 100vh;
  padding: 60px 20px;
  // background-color: #202020;
  // color: #fff;
  display: flex;
  flex-direction: column;
  align-items: center;
  .resume-header {
    width: 100%;
    display: flex;
    justify-content: center;
  }
  .avatar {
    width: 200px;
    height: 200px;
    min-width: 100px;
    border-radius: 50%;
    overflow: hidden;
    object-fit: cover;
    position: relative;
  }

  .avatar-box {
    margin-bottom: 60px;
    width: 200px;
    height: 200px;
    position: relative;
    span {
      width: 32px;
      height: 32px;
      position: absolute;
      left: 0;
      top: 0;
      background-color: #b9ffc4;
      transform: translate(-50px, 120px) scale(1);
      z-index: -2;
      border-radius: 50%;
      //google chrome explore
      -webkit-print-color-adjust: exact;
      //firefox explore
      -moz-print-color-adjust: exact;
      color-adjust: exact;

      &:nth-child(2) {
        background-color: #d8adff;
        transform: translate(200px, 20px) scale(1.5);
      }
      &:nth-child(3) {
        background-color: #ffb940;
        transform: translate(80px, 210px) scale(1.8);
        z-index: 1;
        opacity: 0.8;
      }
    }
    &::before {
      content: '';
      width: 100%;
      height: 100%;
      display: block;
      position: absolute;
      left: 0;
      top: 0;
      border-radius: 50%;
      border: 1px solid #000;
      z-index: -1;
      transform: translate(10px, 10px) scale(1.25);
    }
    &::after {
      content: '';
      width: 100%;
      height: 100%;
      display: block;
      position: absolute;
      left: 0;
      top: 0;
      border-radius: 50%;
      border: 1px solid #000;
      z-index: -1;
      transform: translate(-18px, 8px) scale(1.18);
    }
  }
  .resume {
    max-width: 1080px;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    line-height: 32px;

    .resume_about {
      // font-family: '新细明体';
      letter-spacing: 1px;
      width: 100%;
      display: grid;
      grid-template-columns: 60px 1fr;
      font-size: @fontSize;
      padding: 0 20px;
      margin-bottom: 40px;
      margin-top: 8px;
      .label {
        color: @font-low-color;
      }
      span {
        color: @font-color;
        padding-bottom: 32px;
        font-weight: 700;
      }
    }
    .QRcode {
      width: 100%;
      img {
        width: 400px;
        height: 400px;
      }
    }

    .dev_experience {
      width: 100%;
      padding: 0 20px;
      .exp_parent {
        width: 100%;
        display: flex;
        flex-direction: column;
        .exp_parent-item {
          width: 100%;
          display: flex;
          flex-direction: column;
          &:nth-child(1) > .exp_children {
            .describe::before {
              background-color: @color;
            }
          }

          .exp_children {
            display: flex;
            flex-direction: column;
            margin-bottom: 30px;
            .exp_children-item {
              color: @font-low-color;
              font-size: @fontSize - 4;
              text-indent: 2em;
              padding: 0 15px;
              &:not(:first-child) {
                margin-left: 20px;
              }
            }

            .describe {
              color: @font-color;
              font-size: @fontSize;
              // letter-spacing: 2px;
              line-height: 28px;
              text-indent: 0;
              padding-top: 0;
              display: flex;
              flex-direction: row;
              position: relative;
              word-wrap: break-word;

              &::before {
                content: '';
                display: flex;
                flex-shrink: 0;
                width: 12px;
                height: 12px;
                border-radius: 50%;
                background: #bbbec0;
                margin-right: 10px;
                margin-top: 10px;
              }
            }
          }
        }
      }
    }
  }
}
</style>
