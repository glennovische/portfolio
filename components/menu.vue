<template>
  <div class="header">
    <nav>
      <b-container class="d-flex justify-content-between">
        <Logo />
        <div class="d-flex">
          <SocialIcons />
          <input id="burger" type="checkbox" />

          <label @click="toggleMenu()" class="float-right" for="burger">
            <span></span>
            <span></span>
            <span></span>
          </label>

          <nav :class="{ active: menuActive }">
            <ul :class="{ active: menuActive }">
              <li><nuxt-link to="/">Home</nuxt-link></li>
              <li><nuxt-link to="/fullpage">Full Page</nuxt-link></li>
            </ul>
          </nav>
        </div>
      </b-container>
    </nav>
  </div>
</template>

<script>
import Logo from '@/components/logo.vue'
import SocialIcons from '@/components/SocialIcons.vue'

export default {
  components: {
    Logo,
    SocialIcons
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
@import '~/assets/scss/_colors.scss';

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
    border-radius: 7px;
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
    flex-direction: column;
    justify-content: center;
    left: 20%;
    right: 20%;
    height: 100vh;
    &.active {
      display: flex;
    }
    > li {
      opacity: 0;
      transition: 0.5s;
      transition-delay: 0s;
      > a {
        text-decoration: none;
        text-transform: uppercase;
        color: $white;
        font-size: 80px;
        font-weight: bold;
        font-family: sans-serif;
        display: block;
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
