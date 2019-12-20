<template>
  <div class="header">
    <nav>
      <b-container class="d-flex justify-content-between">
        <Logo />
        <div class="d-flex">
          <HeaderIcons />
          <input id="burger" type="checkbox" />

          <label @click="toggleMenu()" class="float-right" for="burger">
            <span></span>
            <span></span>
            <span></span>
          </label>

          <nav :class="{ active: menuActive }">
            <ul :class="{ active: menuActive }">
              <li><nuxt-link to="/blog">Blog</nuxt-link></li>
              <li><nuxt-link to="/fullpage">Full Page</nuxt-link></li>
              <li><nuxt-link to="/blog">Link #3</nuxt-link></li>
            </ul>
          </nav>
        </div>
      </b-container>
    </nav>
  </div>
</template>

<script>
import Logo from '@/components/logo.vue'
import HeaderIcons from '@/components/HeaderIcons.vue'

export default {
  components: {
    Logo,
    HeaderIcons
  },
  data() {
    return {
      menuActive: false
    }
  },
  methods: {
    toggleMenu() {
      this.menuActive = !this.menuActive
    }
  }
}
</script>

<style lang="scss" scoped>
$white: white;
$primary: #072142;

.white {
  color: $white;
}

.header {
  position: fixed;
  margin-top: 40px;
  z-index: 10;
  width: 100%;
}

input#burger {
  display: none;
}

input + label {
  position: relative;
  height: 27px;
  width: 30px;
  z-index: 5;
  span {
    position: absolute;
    width: 100%;
    height: 4px;
    top: 50%;
    margin-top: -1px;
    left: 0;
    display: block;
    background: $white;
    transition: 0.5s;
  }
  span:first-child {
    top: 3px;
  }
  span:last-child {
    top: 26px;
  }
}
label:hover {
  cursor: pointer;
}
input:checked + label {
  span {
    opacity: 0;
    top: 50%;
  }
  span:first-child {
    opacity: 1;
    transform: rotate(405deg);
  }
  span:last-child {
    opacity: 1;
    transform: rotate(-405deg);
  }
}
input ~ nav {
  background: $primary;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 1px;
  z-index: 3;
  transition: 0.5s;
  transition-delay: 0.5s;
  overflow: hidden;
  &.active {
    background-color: $primary;
  }
  > ul {
    display: none;
    text-align: center;
    list-style: none;
    position: absolute;
    top: 35%;
    left: 20%;
    right: 20%;
    &.active {
      display: block;
    }
    > li {
      opacity: 0;
      transition: 0.5s;
      transition-delay: 0s;
      > a {
        text-decoration: none;
        text-transform: uppercase;
        color: $white;
        font-weight: 700;
        font-family: sans-serif;
        display: block;
        padding: 30px;
      }
    }
  }
}
input:checked ~ nav {
  height: 100%;
  transition-delay: 0s;
  > ul {
    > li {
      opacity: 1;
      transition-delay: 0.5s;
    }
  }
}
</style>
