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
          name: '主題名稱1',
          id: 1,
          projects: [
            {
              title: '作品集1',
              desc: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut,molestiae?',
              cover: 'test.png',
              githubLink: '#',
              codepenLink: '#',
              blogLink: '#',
              demoLink: '#',
              demoRoute: '',
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Testing']
            },
            {
              title: '作品集2',
              desc: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut,molestiae?',
              cover: 'test.png',
              githubLink: '#',
              codepenLink: '#',
              blogLink: '#',
              demoLink: '#',
              demoRoute: '',
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Testing']
            }
            ,
            {
              title: '作品集3',
              desc: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut,molestiae?',
              cover: 'test.png',
              githubLink: '#',
              codepenLink: '#',
              blogLink: '#',
              demoLink: '#',
              demoRoute: '',
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Testing']
            }
          ]
        },
        {
          name: '主題名稱2',
          id: 2,
          projects: [
            {
              title: '作品集4',
              desc: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut,molestiae?',
              cover: 'test.png',
              githubLink: '#',
              codepenLink: '#',
              blogLink: '#',
              demoLink: '#',
              demoRoute: '',
              tags: ['Vue.js', 'Sass/SCSS', 'RWD', 'Testing']
            },
            {
              title: '作品集5',
              desc: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut,molestiae?',
              cover: 'test.png',
              githubLink: '#',
              codepenLink: '#',
              blogLink: '#',
              demoLink: '#',
              demoRoute: '',
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
  gap: 30px;
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