<template>
  <nav>
    <h1 class="nav-title"><router-link to="home">Dolly Chen</router-link></h1>
    <ul class="nav-list">
      <li class="nav-list__item">
        <a href="＃" target="_blank">Resume</a>
      </li>
      <li class="nav-list__item">
        <router-link to="home">Portfolio</router-link>
      </li>
      <li class="nav-list__item">
        <a href="https://github.com/DollyChen-CYC" target="_blank">Github</a>
      </li>
      <li class="nav-list__item">
        <a href="https://dollychen-yiching.medium.com/" target="_blank">Blog</a>
      </li>
      <li class="nav-list__item">
        <a
          href="https://www.linkedin.com/in/dolly-yiching-chen/"
          target="_blank"
          >Linkedin</a
        >
      </li>
    </ul>
  </nav>
</template>

<style lang="scss" scoped>
nav {
  background: #0e76a8;
  padding: 20px 30px;
  color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;

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

  .nav-list {
    list-style-type: none;
    display: flex;
    gap: 20px;
    font-weight: 500;
    font-size: 18px;
  }
}
</style>
