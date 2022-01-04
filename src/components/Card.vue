<template>
  <div class="card">
    <div class="card__body">
      <img
        :src="require('../assets/images/' + cardInfo.cover)"
        alt=""
        class="card__body__cover"
      />
      <div class="card__body__content-wrapper">
        <h2 class="card__body__content-wrapper__title">{{ cardInfo.title }}</h2>
        <div class="card__body__content-wrapper__tag-wrapper">
          <span
            v-for="tag in cardInfo.tags"
            :key="tag"
            class="card__body__content-wrapper__tag-wrapper__tag"
          >
            {{ tag }}
          </span>
        </div>
        <h4 class="card__body__content-wrapper__desc">
          {{ cardInfo.desc }}
        </h4>
      </div>
    </div>
    <div class="card__footer">
      <div class="card__footer__project-links">
        <span v-if="cardInfo.githubLink"
          ><a :href="cardInfo.githubLink">Github</a></span
        >
        <span v-if="cardInfo.codepenLink"
          ><a :href="cardInfo.codepenLink">CodePen</a></span
        >
        <span v-if="cardInfo.blogLink"
          ><a :href="cardInfo.blogLink">Blog</a></span
        >
      </div>
      <a
        v-if="cardInfo.demoLink.length !== 0"
        :href="cardInfo.demoLink"
        class="card__footer__demo-link"
      >
        <div class="card__footer__demo-link__triangle">&#9654;</div>
      </a>
      <router-link
        v-else
        :to="cardInfo.demoRoute"
        class="card__footer__demo-link"
      >
        <div class="card__footer__demo-link__triangle">&#9654;</div>
      </router-link>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Card',
  props: {
    cardInfo: {
      type: Object,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

a {
  text-decoration: none;
  color: inherit;
  cursor: pointer;
  &:hover,
  &:active {
    color: inherit;
    text-decoration: underline;
    outline: none;
  }
}

.card {
  width: 500px;
  height: 300px;
  border-radius: 30px;
  overflow: hidden;
  box-shadow: inset 0 4px 7px 1px #ffffff,
    inset 0 -5px 20px rgba(173, 186, 204, 0.25), 0 2px 6px rgba(0, 21, 64, 0.14),
    0 10px 20px rgba(0, 21, 64, 0.05);
  transition: box-shadow 0.1s linear;
  &:hover,
  &:active {
    box-shadow: 3px 4px 15px 3px rgba(60, 64, 71, 0.24);
    .card__body__content-wrapper {
      opacity: 1;
    }
    .card__footer__project-links {
      color: #0e76a8;
    }
  }

  &__body {
    width: 100%;
    height: 75%;
    position: relative;
    &__cover {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    &__content-wrapper {
      position: absolute;
      z-index: 1;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 25px 30px;
      background-color: rgba(66, 66, 66, 0.85);
      color: #fff;
      letter-spacing: 1px;
      opacity: 0;
      transition: opacity 0.25s linear;
      &__title {
        margin-bottom: 20px;
      }

      &__tag-wrapper {
        position: absolute;
        top: 30px;
        right: 35px;
        font-size: 12px;
        font-weight: 600;
        display: flex;
        gap: 8px;

        &__tag {
          padding: 4px 8px;
          background-color: #fff;
          border-radius: 10px;
          color: rgb(100, 100, 100);
        }
      }

      &__desc {
        line-height: 1.6;
      }
    }
  }

  &__footer {
    height: 25%;
    width: 100%;
    position: relative;
    padding: 0 30px;
    display: flex;
    align-items: center;
    gap: 20px;

    &__project-links {
      display: flex;
      gap: 20px;
      transition: all 0.25s linear;
    }

    &__demo-link {
      height: 85px;
      width: 85px;
      position: absolute;
      right: 30px;
      top: 0;
      z-index: 2;
      border-radius: 50%;
      border-radius: 30px solid rgba(150, 150, 150, 0.3);
      background-color: #fff;
      box-shadow: 0 2px 6px rgba(0, 21, 64, 0.14),
        0 10px 20px rgba(61, 65, 73, 0.05), inset 0 4px 7px 1px #ffffff;
      transform: translateY(-50%);
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: box-shadow 0.1s linear;

      &__triangle {
        font-size: 36px;
        color: #0e76a8;
        transform: translateX(5px);
      }

      &:hover,
      &:active {
        text-decoration: none;
        box-shadow: 2px 3px 8px 2px rgba(59, 66, 82, 0.24);
      }

      &:active {
        .card__footer__demo-link__triangle {
          color: #333;
        }
      }
    }
  }
}
</style>