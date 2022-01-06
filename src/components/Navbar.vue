<template>
  <nav>
    <h1 class="nav-title"><router-link to="home">Dolly Chen</router-link></h1>
    <ul class="nav-list">
      <li class="nav-list__item">
        <a href="https://dollychen-cyc.github.io/DollyChen-CYC/src/doc/%E9%99%B3%E5%84%80%E7%92%9F%20-%20%E4%B8%AD%E6%96%87%E5%B1%A5%E6%AD%B7.pdf" target="_blank">Resume</a>
      </li>
      <!-- <li class="nav-list__item">
        <router-link to="home">Portfolio</router-link>
      </li> -->
      <li class="nav-list__item">
        <a href="https://github.com/DollyChen-CYC" target="_blank" >Github</a>
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
