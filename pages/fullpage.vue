<template>
  <div>
    <Menu />
    <full-page :options="options" id="fullpage" ref="fullpage">
      <div class="section">
        <h3>vue-fullpage.js</h3>
      </div>
      <div class="section">
        <div class="slide">
          <h3>Slide 2.1</h3>
        </div>
        <div class="slide">
          <h3>Slide 2.2</h3>
        </div>
        <div class="slide">
          <h3>Slide 2.3</h3>
        </div>
      </div>
      <div class="section">
        <h3>Section 3</h3>
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
        afterLoad: this.afterLoad,
        navigation: true,
        anchors: ['page1', 'page2', 'page3'],
        sectionsColor: [
          '#41b883',
          '#ff5f45',
          '#0798ec',
          '#fec401',
          '#1bcee6',
          '#ee1a59',
          '#2c3e4f',
          '#ba5be9',
          '#b4b8ab'
        ]
      }
    }
  },
  methods: {
    afterLoad(origin, destination, direction) {
      console.log('After load....')
      console.log(destination)
    },
    addSection(e) {
      const newSectionNumber =
        document.querySelectorAll('.fp-section').length + 1

      // creating the section div
      const section = document.createElement('div')
      section.className = 'section'
      section.innerHTML = `<h3>Section ${newSectionNumber}</h3>`

      // adding section
      document.querySelector('#fullpage').appendChild(section)

      // creating the section menu element
      const sectionMenuItem = document.createElement('li')
      sectionMenuItem.setAttribute('data-menuanchor', 'page' + newSectionNumber)
      sectionMenuItem.innerHTML = `<a href="#page${newSectionNumber}">Section${newSectionNumber}</a>`

      // adding anchor for the section
      this.options.anchors.push(`page${newSectionNumber}`)

      // we have to call `update` manually as DOM changes won't fire updates
      // requires the use of the attribute ref="fullpage" on the
      // component element, in this case, <full-page>
      // ideally, use an ID element for that element too
      this.$refs.fullpage.build()
    },

    removeSection() {
      const sections = document
        .querySelector('#fullpage')
        .querySelectorAll('.fp-section')
      const lastSection = sections[sections.length - 1]

      // removing the last section
      lastSection.parentNode.removeChild(lastSection)

      // removing the last anchor
      this.options.anchors.pop()

      // removing the last item on the sections menu
      const sectionsMenuItems = document.querySelectorAll('#menu li')
      const lastItem = sectionsMenuItems[sectionsMenuItems.length - 1]
      lastItem.parentNode.removeChild(lastItem)
    }
  }
}
</script>

<style lang="scss" scoped></style>
