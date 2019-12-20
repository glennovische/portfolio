<template>
  <div>
    <Menu />
    <full-page :options="options">
      <div class="section">
        <div class="container">
          <div class="title title--top">
            <h1 class="title__text js-letter">Glenn<br />Dutrieux</h1>
          </div>
        </div>
      </div>
      <div class="section"></div>
      <div class="section ">
        <div class="container">
          third section ...
        </div>
      </div>
    </full-page>
  </div>
</template>

<script>
import Menu from '@/components/menu.vue'

export default {
  components: {
    Menu
  },
  data() {
    return {
      options: {
        sectionsColor: ['#41b883', '#ff5f45', '#ff4d5a']
      }
    }
  }
}
</script>

<style lang="scss" scoped></style>
