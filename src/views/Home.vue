<template>
  <div class="home">
    <h1 class="headline">作品集</h1>
    <!-- Section v-for start -->
    <section
      v-for="category in portfolio"
      :key="category.id"
      class="category-section"
    >
      <h2 class="category-section__headline">{{ category.name }}</h2>
      <h4 class="category-section__desc">{{ category.description }}</h4>
      <div class="category-section__project-wrapper">
        <!-- Card v-for start -->
        <div v-for="project in category.projects" :key="project.title">
          <Card :card-info="project" />
        </div>
        <!-- Card v-for end -->
      </div>
    </section>
    <!-- Section v-for end -->
  </div>
</template>

<script>
import Card from '../components/Card.vue'

export default {
  name: 'Home',
  components: {
    Card,
  },
  data() {
    return {
      portfolio: [
        {
          name: 'Vue.js 作品',
          id: 1,
          description: '使⽤前端框架 (Vue.js) 和 CSS 預處理程器 (Sass/SCSS) 建⽴的 SPA (Single-page application)',
          projects: [
            {
              title: '協作專案 - Alphitter 社群網站(前端)',
              desc: '前、後端分離的 Sprint 團隊開發專案，模擬社群網站，包含註冊、登入、登出、發文、回覆、追蹤、按讚、修改個人資料...等功能。 (測試帳號/密碼：user1/12345678) ',
              cover: '1-alphitter.png',
              githubLink: 'https://github.com/sh330035/twitter-frontend',
              codepenLink: '',
              blogLink: 'https://dollychen-yiching.medium.com/%E8%AA%B2%E7%A8%8B%E7%9A%84%E7%B5%82%E9%BB%9E-%E6%98%AF%E4%BA%BA%E7%94%9F%E6%94%B9%E8%AE%8A%E7%9A%84%E8%B5%B7%E9%BB%9E-c1b0517501c8?p=c1b0517501c8',
              demoLink: 'https://sh330035.github.io/twitter-frontend/',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Vue.js', 'Sass/SCSS', 'RESTful API', 'Axios']
            },
            {
              title: '餐廳論壇',
              desc: '使⽤ Vue.js 並串接 RESTful API 所建⽴的餐廳論壇。前台提供使用者註冊、登入/登出、收藏餐廳、新增評論、按讚、修改個人資料...等功能，並提供後台進行新增/刪除/修改功能。 (測試帳號/密碼：user1/12345678)',
              cover: '2-restaurant-forum.png',
              githubLink: 'https://github.com/DollyChen-CYC/Restaurant-Forum',
              codepenLink: '',
              blogLink: '',
              demoLink: 'https://dollychen-cyc.github.io/Restaurant-Forum/#/signin',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Bootstrap']
            }
            ,
            {
              title: '電商結帳頁面切版',
              desc: '應⽤ Vue 框架和 Sass/SCSS 切版，納入 RWD 設計適應不同裝置，刻意將表單步驟拆分，並提供 dark mode，讓身處不同使用環境的 user 皆能有良好的使⽤者體驗。',
              cover: '3-checkout-page.png',
              githubLink: 'https://github.com/DollyChen-CYC/Checkout-Page_vue',
              codepenLink: '',
              blogLink: 'https://dollychen-yiching.medium.com/%E5%B0%88%E6%A1%88%E4%BB%8B%E7%B4%B9-checkout-page-16c0da7d75fe',
              demoLink: 'https://dollychen-cyc.github.io/Checkout-Page_vue/#/checkout',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Dark Mode']
            }
          ]
        },
        {
          name: 'RWD 網頁作品',
          id: 2,
          description: '應⽤ HTML/CSS, JavaScript (ES6) 實踐網⾴切版，透過 RWD 響應式網⾴設計建⽴使⽤者體驗良好的介面',
          projects: [
            {
              title: 'T-shirt Store 電商網頁切版',
              desc: '使用 HTML/CSS 切版商品呈列頁面，運用 CSS Grid 和 Flexbox 實踐 RWD 排版，讓不同裝置的使用者皆有良好的瀏覽體驗。按鈕與商品圖等元件皆有微互動設計，增加互動趣味性。',
              cover: '4-TSHIRT-STORE.png',
              githubLink: '',
              codepenLink: 'https://codepen.io/dollychen_yiching/pen/rNwpwPo',
              blogLink: 'https://dollychen-yiching.medium.com/ac-%E5%AD%B8%E6%9C%9F-2-3-%E9%9B%BB%E5%95%86%E7%B6%B2%E9%A0%81%E5%88%87%E7%89%88-%E9%9D%A2%E8%A9%A6%E6%A8%A1%E6%93%AC-618ce68f4865?p=618ce68f4865',
              demoLink: 'https://codepen.io/dollychen_yiching/full/rNwpwPo',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['HTML/CSS', 'RWD', 'Grid', 'Flexbox']
            },
            {
              title: '飲料店 POS 點餐機',
              desc: '以 JS 物件導向為實作重點的飲料點餐機，利用原型繼承 (prototypal inheritance) 概念，使用建構函式 (Constructor Function) 的共用方法新增飲料訂單。',
              cover: '5-drinks-POS.png',
              githubLink: 'https://github.com/DollyChen-CYC/Drinks-POS/blob/main/main.js',
              codepenLink: '',
              blogLink: '',
              demoLink: 'https://dollychen-cyc.github.io/Drinks-POS/',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Vanilla JS', 'OOP', 'POS']
            },
            {
              title: '卡片配對記憶遊戲',
              desc: '應⽤ HTML/CSS, JavaScript 建立的卡片配對記憶遊戲，使用 MVC 模式來管理程式碼，並使用狀態來控制程式流程',
              cover: '6-card-matching.png',
              githubLink: '',
              codepenLink: 'https://codepen.io/dollychen_yiching/pen/xxrxvQv',
              blogLink: 'https://dollychen-yiching.medium.com/%E5%AD%B8%E7%BF%92%E5%9B%9E%E9%A1%A72-%E7%A8%8B%E5%BC%8F%E5%AD%B8%E7%BF%92%E5%BF%83%E8%B7%AF%E7%B4%80%E9%8C%84-eaeabdc5a6e9?p=eaeabdc5a6e9',
              demoLink: 'https://codepen.io/dollychen_yiching/full/xxrxvQv',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['HTML/CSS', 'JavaScript', 'MVC']
            },
            {
              title: 'RGB to HEX 色碼轉換器',
              desc: '使用HTML/CSS, JavaScript 建立的簡易色碼轉換器',
              cover: '7-rgb-to-hex.png',
              githubLink: '',
              codepenLink: 'https://codepen.io/dollychen_yiching/pen/YzVVmKZ',
              blogLink: 'https://dollychen-yiching.medium.com/%E8%88%87-alpha-camp-%E4%B8%80%E8%B5%B7%E8%B6%85%E9%80%9F%E5%AD%B8%E7%BF%92-e9f101fa1394',
              demoLink: 'https://codepen.io/dollychen_yiching/full/YzVVmKZ',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['HTML', 'CSS', 'JS']
            }
          ]
        },
        {
          name: 'Bootstrap 作品',
          id: 3,
          description: '使用 Bootstrap 框架建立的響應式網頁作品',
          projects: [
            {
              title: '交友社群平台',
              desc: '使用 Bootstrap 框架建立的簡易交友社群頁面，可瀏覽、搜尋所有用戶，點擊頭貼查看用戶資訊，且可將用戶加至好友聯絡清單中。',
              cover: '8-bootstrap-find-friends.png',
              githubLink: 'https://github.com/DollyChen-CYC/Bootstrap-Projects/tree/main/03%20social%20media%20page%20-%20findFriends%2B',
              codepenLink: 'https://codepen.io/dollychen_yiching/project/editor/AaqONB',
              blogLink: 'https://dollychen-yiching.medium.com/%E5%AD%B8%E7%BF%92%E5%9B%9E%E9%A1%A72-%E7%A8%8B%E5%BC%8F%E5%AD%B8%E7%BF%92%E5%BF%83%E8%B7%AF%E7%B4%80%E9%8C%84-eaeabdc5a6e9?p=eaeabdc5a6e9',
              demoLink: 'https://codepen.io/dollychen_yiching/project/full/AaqONB',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Bootstrap', 'JavaScript', 'Axios']
            },
            {
              title: '電影清單',
              desc: '使用 Bootstrap 建立的電影資訊頁面，可以清單或圖片 2 種方式來瀏覽、搜尋所有電影，點擊 More 查看詳細電影介紹，並可將電影加至收藏區中。',
              cover: '9-movie-list.png',
              githubLink: 'https://github.com/DollyChen-CYC/Bootstrap-Projects/tree/main/04%20Movie%20list',
              codepenLink: '',
              blogLink: 'https://dollychen-yiching.medium.com/%E5%AD%B8%E7%BF%92%E5%9B%9E%E9%A1%A72-%E7%A8%8B%E5%BC%8F%E5%AD%B8%E7%BF%92%E5%BF%83%E8%B7%AF%E7%B4%80%E9%8C%84-eaeabdc5a6e9?p=eaeabdc5a6e9',
              demoLink: 'https://dollychen-cyc.github.io/Bootstrap-Projects/04%20Movie%20list/index.html',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Bootstrap', 'JavaScript', 'RWD', 'Axios']
            }
          ]
        },
        {
          name: 'Mini-Projects with Creative UI ',
          id: 4,
          description: '使用 HTML, CSS 以及 Vanilla JavaScript 建立獨特且富有創意的動畫與 UI',
          projects: [
            {
              title: '趣味性的導覽列呈現',
              desc: '點擊左上的導覽列圖示，感受趣味性的導覽列動畫與排版吧！',
              cover: '10-rotating-navigation.png',
              githubLink: 'https://github.com/DollyChen-CYC/Mini-Web-Projects-50-Days-Challenge/tree/main/03day_rotating_navigation',
              codepenLink: 'https://codepen.io/dollychen_yiching/pen/PomexxR',
              blogLink: '',
              demoLink: 'https://dollychen-cyc.github.io/Mini-Web-Projects-50-Days-Challenge/03day_rotating_navigation/',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['HTML', 'CSS', 'JavaScript']
            },
            {
              title: '捲軸滑動特效',
              desc: '應用 CSS transform 和 transition 特性完成的動態團隊介紹頁面。頁面開啟時，兩側的裝飾圖片會以漸速滑入，當使用者拉動卷軸往下瀏覽團隊資訊時，成員卡片會由兩側飛入。',
              cover: '13-scroll-animation.png',
              githubLink: 'https://github.com/DollyChen-CYC/Mini-Web-Projects-50-Days-Challenge/tree/main/06day_scroll_animation',
              codepenLink: 'https://codepen.io/dollychen_yiching/pen/YzVRQRM',
              blogLink: '',
              demoLink: 'https://dollychen-cyc.github.io/Mini-Web-Projects-50-Days-Challenge/06day_scroll_animation/',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Testing']
            },
            {
              title: '頁面載入倒數動畫',
              desc: '背景使用模糊特效處理的頁面載入倒數動畫，當頁面尚未載入完全時為模糊狀態，隨著載入的百分比趨近 100%，畫面會漸漸轉為清晰。',
              cover: '12-blurry-loading.png',
              githubLink: 'https://github.com/DollyChen-CYC/Mini-Web-Projects-50-Days-Challenge/tree/main/05day_Blurry%20Loading',
              codepenLink: 'https://codepen.io/dollychen_yiching/pen/zYwmvOP',
              blogLink: '',
              demoLink: 'https://dollychen-cyc.github.io/Mini-Web-Projects-50-Days-Challenge/05day_Blurry%20Loading/',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['HTML', 'CSS', 'JavaScript']
            },
            {
              title: '簡約帥氣的搜尋頁面',
              desc: '點擊搜尋按鈕，體驗簡約時髦的搜尋條設計。',
              cover: '11-hidden-search-bar.png',
              githubLink: 'https://github.com/DollyChen-CYC/Mini-Web-Projects-50-Days-Challenge/tree/main/04day_hidden_search_widget',
              codepenLink: 'https://codepen.io/dollychen_yiching/pen/MWmXwWp',
              blogLink: '',
              demoLink: 'https://dollychen-cyc.github.io/Mini-Web-Projects-50-Days-Challenge/04day_hidden_search_widget/',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['HTML', 'CSS', 'JavaScript']
            }
          ]
        },
        {
          name: 'Express.js 作品',
          id: 5,
          description: '在 Node.js 環境下以 Express 框架和 Handlebars 樣板引擎搭配 MongoDB 建⽴基本的網⾴',
          projects: [
            {
              title: '作品集10',
              desc: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut,molestiae?',
              cover: 'test.png',
              githubLink: '#',
              codepenLink: '#',
              blogLink: '#',
              demoLink: '',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Testing']
            },
            {
              title: '作品集11',
              desc: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut,molestiae?',
              cover: 'test.png',
              githubLink: '#',
              codepenLink: '#',
              blogLink: '#',
              demoLink: '',
              demoRoute: '',
              customizedLink: {
                infoTitle: '',
                link: ''
              },
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Testing']
            }
          ]
        },
        {
          name: 'React.js 作品 (Coming soon...)',
          id: 6,
          description: '使用 React 框架，運用 React-Router, Redux, 和 Hook 建立建⽴的 SPA (Single-page application)',
          projects: [
            {
              title: '作品集12',
              desc: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut,molestiae?',
              cover: 'test.png',
              githubLink: '',
              codepenLink: '',
              blogLink: '',
              demoLink: '',
              demoRoute: '',
              customizedLink: {
                infoTitle: 'Coming Soon...',
                link: ''
              },
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Testing']
            }
          ]
        }
      ],

    }
  }
}
</script>

<style lang="scss" scoped>
.home {
  width: 100vw;
  min-width: 540px;
  height: 100%;
  padding: 50px 80px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  background-color: #fdfdfd;
  overflow-x: hidden;

  cursor: default;

  h1 {
    font-size: 36px;
  }

  h2 {
    font-size: 28px;
    color: #0e76a8;
  }

  .category-section {
    &__headline {
      margin: 15px 0;
    }

    &__desc {
      margin: 15px 0;
      padding: 0px 20px;
      font-weight: 400;
      font-size: 20px;
    }

    &__project-wrapper {
      position: relative;
      left: -80px;
      width: 100vw;
      padding: 10px 100px 25px;
      display: flex;
      flex-flow: row nowrap;
      overflow-x: auto;
      overflow-y: hidden;
      gap: 30px;

      &::-webkit-scrollbar {
        display: none;
      }
      &::-webkit-scrollbar {
        background: transparent;
      }
      &::-webkit-scrollbar-thumb {
        background-color: transparent;
      }
    }
  }
}
</style>