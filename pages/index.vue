<template>
  <div>
    <Menu />

    <div>
      <p
        v-if="isNotContact"
        class="scroll-down"
        style="transform: translateY(0%);"
      >
        SCROLLDOWN
      </p>
    </div>
    <full-page :options="options">
      <div class="section work">
        <div v-show="section1Active" class="slide">
          <LeftContent>
            <template v-slot:title>
              GTM
            </template>
            <template v-slot:subtitle>
              Webshop
            </template>
            <template v-slot:content>
              <button class="btn" href="">Show me more</button>
            </template>
          </LeftContent>
          <RightContent image-class="image--works">
            <template v-slot:number>
              01
            </template>
          </RightContent>
        </div>
      </div>
      <div
        :class="{ 'restart-animation': restartAnimation2 }"
        class="section about"
      >
        <div v-show="section2Active" class="slide">
          <LeftContent>
            <template v-slot:title>
              About me
            </template>
            <template v-slot:subtitle>
              I love Front-End <br />
              & Design
            </template>
            <template v-slot:content>
              <button class="btn" href="">Show me more</button>
            </template>
          </LeftContent>
          <RightContent image-class="image--design">
            <template v-slot:number>
              02
            </template>
          </RightContent>
        </div>
      </div>
      <div class="section contact">
        <div v-show="section3Active" class="slide">
          <LeftContent>
            <template v-slot:title>
              Get In Touch
            </template>
            <template v-slot:subtitle>
              <a href="mailto:dutrieux.glenn@gmail.com"
                >dutrieux.glenn@gmail.com</a
              >
            </template>
            <template v-slot:content>
              <SocialIcons />
            </template>
          </LeftContent>
          <RightContent image-class="image--about">
            <template v-slot:number>
              03
            </template>
          </RightContent>
        </div>
      </div>
    </full-page>
  </div>
</template>

<script>
import Menu from '@/components/menu.vue'
import LeftContent from '@/components/LeftContent'
import RightContent from '@/components/RightContent'
import SocialIcons from '@/components/SocialIcons'

export default {
  components: {
    Menu,
    LeftContent,
    RightContent,
    SocialIcons
  },
  data() {
    return {
      section1Active: true,
      section2Active: false,
      section3Active: false,
      isNotContact: true,
      restartAnimation1: false,
      restartAnimation2: false,
      restartAnimation3: false,
      options: {
        afterLoad: this.afterLoad,
        onLeave: this.onLeave,
        navigation: true,
        sectionsColor: ['#072142', '#072142', '#072142']
      }
    }
  },
  methods: {
    onLeave(origin, destination, direction) {
      const scrolldown = document.querySelector('.scroll-down')

      // Dit is 2
      if (origin.index === 0 && direction === 'down') {
        this.section1Active = false
        this.section2Active = true

        this.isNotContact = true
        // Dit is terug naar 1
      } else if (origin.index === 1 && direction === 'up') {
        this.section1Active = true
        this.section2Active = false
        this.isNotContact = true
        // Dit is van 2 naar 3
      } else if (origin.index === 1 && direction === 'down') {
        this.section3Active = true
        this.section2Active = false

        scrolldown.style.transform = 'translateY(180%)'
        scrolldown.style.animationDuration = '1.5s'
        this.isNotContact = false
        // Dit is van 3 naar 2
      } else if (origin.index === 2 && direction === 'up') {
        this.section3Active = false
        this.section2Active = true
        this.isNotContact = true
      }
    }
  },

  afterLoad(origin, destination, direction) {
    // const about = document.querySelector('.about')
    // const work = document.querySelector('.work')
    // const contact = document.querySelector('.contact')

    if (origin.index === 0) {
      alert('Section 1 ended loading')
    }

    if (origin.index === 1) {
      alert('Section 2 ended loading')
    }

    if (origin.index === 2) {
      alert('Section 3 ended loading')
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~/assets/scss/_colors.scss';

#callbacks-placeholder {
  position: fixed;
  top: 50px;
  left: 50px;
  color: black;
  z-index: 999;
}

.scroll-down {
  position: fixed;
  font-size: 14px;
  bottom: 65px;
  left: 40px;
  line-height: 1;
  letter-spacing: 0.3em;
  writing-mode: vertical-rl;
  color: $white;
  z-index: 4;
  animation: ScrollDown 1.5s;
  &:after {
    content: '';
    width: 2px;
    height: 50px;
    background: #fff;
    position: absolute;
    left: 0;
    right: 0;
    margin: auto;
    bottom: -80px;
  }
}

/deep/.section {
  &:nth-child(1) {
    &.active {
      background-color: red;
      .scroll-down & {
        display: none;
      }
    }
  }
}

@keyframes ScrollDown {
  from {
    transform: translateY(100%) translateZ(0px);
  }
  to {
    transform: translateY(0%) translateZ(0px);
  }
}

@keyframes ScrollUp {
  from {
    transform: translateY(0%) translateZ(0px);
  }
  to {
    transform: translateY(100%) translateZ(0px);
  }
}
</style>
