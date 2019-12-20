<template>
  <div>
    <Menu />
    <div class="fullpage__slide">
      <div class="moon">
        <div
          class="moon__img js-parallax-moon"
          style="transform: translate3d(0px, 0px, 0px) rotate(0.0001deg); transform-style: preserve-3d; backface-visibility: hidden; pointer-events: none;"
        >
          <div
            class="moon__front layer"
            data-depth="0.2"
            style="transform: translate3d(-10.4px, 3.9px, 0px); transform-style: preserve-3d; backface-visibility: hidden; position: relative; display: block; left: 0px; top: 0px;"
          >
            <div class="moon__text-wrap">
              <p
                class="moon__text js-moon"
                data-depth="0.5"
                style="opacity: 1; transform: translateX(0%) translateZ(0px);"
              >
                PORTFOLIO
              </p>
            </div>
          </div>
          <div
            class="moon__front layer"
            data-depth="0.8"
            style="transform: translate3d(-41.8px, 15.8px, 0px); transform-style: preserve-3d; backface-visibility: hidden; position: absolute; display: block; left: 0px; top: 0px;"
          >
            <div
              class="cloud cloud--front1 js-moon"
              style="opacity: 1; transform: translateX(0%) translateZ(0px);"
            >
              <img src="../assets/img/cloud1.svg" alt="cloud" />
            </div>
          </div>
          <div
            class="moon__back layer"
            data-depth="0.4"
            style="transform: translate3d(-20.9px, 7.9px, 0px); transform-style: preserve-3d; backface-visibility: hidden; position: absolute; display: block; left: 0px; top: 0px;"
          >
            <div
              class="cloud cloud--back2 js-moon"
              style="opacity: 1; transform: translateX(0%) translateZ(0px);"
            >
              <img src="../assets/img/b_cloud02.svg" alt="cloud" />
            </div>
          </div>
          <div
            class="moon__front layer"
            data-depth="0.6"
            style="transform: translate3d(-31.3px, 11.8px, 0px); transform-style: preserve-3d; backface-visibility: hidden; position: absolute; display: block; left: 0px; top: 0px;"
          >
            <div
              class="cloud cloud--front2 js-moon"
              style="opacity: 1; transform: translateX(0%) translateZ(0px);"
            >
              <img src="../assets/img/cloud2.svg" alt="cloud" />
            </div>
          </div>
          <div
            class="moon__back layer"
            data-depth="0.5"
            style="transform: translate3d(-26.1px, 9.9px, 0px); transform-style: preserve-3d; backface-visibility: hidden; position: absolute; display: block; left: 0px; top: 0px;"
          >
            <img
              class="js-moon"
              src="../assets/img/moon.svg"
              alt="moon"
              style="opacity: 1; transform: translateX(0%) translateZ(0px);"
            />
          </div>
          <div
            class="moon__front layer"
            data-depth="0.7"
            style="transform: translate3d(-36.6px, 13.8px, 0px); transform-style: preserve-3d; backface-visibility: hidden; position: absolute; display: block; left: 0px; top: 0px;"
          >
            <div
              class="cloud cloud--front3 js-moon"
              style="opacity: 1; transform: translateX(0%) translateZ(0px);"
            >
              <img src="../assets/img/cloud3.svg" alt="cloud" />
            </div>
          </div>
          <div
            class="moon__back layer"
            data-depth="0.3"
            style="transform: translate3d(-15.7px, 5.9px, 0px); transform-style: preserve-3d; backface-visibility: hidden; position: absolute; display: block; left: 0px; top: 0px;"
          >
            <div
              class="cloud cloud--back1 js-moon"
              style="opacity: 1; transform: translateX(0%) translateZ(0px);"
            >
              <img src="../assets/img/b_cloud01.svg" alt="cloud" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="sky-color"></div>
  </div>
</template>

<script>
import Menu from '@/components/menu.vue'

export default {
  components: {
    Menu
  }
}
</script>

<style lang="scss" scoped>
.sky-color {
  position: fixed;
  width: 100%;
  height: 100vh;
  top: 0;
  left: 0;
  background-image: linear-gradient(
    to bottom,
    #072142,
    #061c37,
    #07182b,
    #061220,
    #020b16
  );
  z-index: -200;
}

.fullpage__slide {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  color: #fff;
}

.moon {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 29.427%;
  margin: auto;
  height: 1385px;
  width: 1385px;
  display: flex;
  align-items: center;
  justify-content: center;
  &__text-wrap {
    position: absolute;
    left: -15.5963%;
    top: 50%;
    transform: translate3d(0, -50%, 0);
  }
  &__text {
    font-size: 6.4rem;
    letter-spacing: 0.1em;
    text-shadow: 0 10px 15px rgba(2, 11, 22, 0.2);
    color: #ff4d5a;
  }
  &__img {
    position: relative;
    width: 39.350180505%;
    height: 39.350180505%;
  }
  &__front {
    z-index: 200;
  }
  &__back {
    z-index: -100;
  }
}

.cloud {
  position: absolute;
  &--back1 {
    top: -22.38532%;
    right: -7.706422%;
    width: 69.724%;
  }
}

.layer {
  width: 100%;
  height: 100%;
}

.image .page-num {
  position: absolute;
  overflow-y: hidden;
  right: -7.549%;
  bottom: 12.3762%;
  font-size: 15rem;
  color: #fff;
  font-family: 'Abril Fatface';
  z-index: 200;
}
@media screen and (max-width: 800px) {
  .image .page-num {
    font-size: 7.5rem;
    right: -5%;
  }
}
@media screen and (max-width: 420px) {
  .image .page-num {
    display: none;
  }
}
.image .page-num p {
  line-height: 1.1;
  text-shadow: 0 10px 30px rgba(2, 11, 22, 0.5);
}
@media screen and (max-width: 420px) {
  .image .page-num p {
    text-shadow: 0 3px 10px rgba(2, 11, 22, 0.5);
  }
}
.moonlight {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 29.427%;
  margin: auto;
  height: 1385px;
  width: 1385px;
  z-index: -100;
}
@media screen and (max-width: 800px) {
  .moonlight {
    width: 100vw;
    height: 100vw;
    left: 23%;
  }
}
@media screen and (max-width: 420px) {
  .moonlight {
    width: 165vw;
    height: 165vw;
    left: 50%;
    top: -10rem;
    bottom: auto;
    -webkit-transform: translate3d(-50%, 0, 0);
    transform: translate3d(-50%, 0, 0);
  }
}
.moonlight__wrap {
  width: 100%;
  height: 100%;
}
.moonlight__img {
  background-size: 100%;
}
.moon-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  z-index: -100;
}
@media screen and (max-width: 420px) {
  .moon-background {
    height: 100%;
    bottom: 0;
    margin: auto;
    max-height: 667px;
  }
}
.star {
  width: 1300px;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 29.427%;
  z-index: -100;
}
@media screen and (max-width: 800px) {
  .star {
    width: 100vw;
    left: 23%;
  }
}
@media screen and (max-width: 420px) {
  .star {
    left: 0;
  }
}
.star__img {
  width: 100%;
  height: 100%;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}
@media screen and (max-width: 420px) {
  .star__img {
    display: block;
  }
}
@media screen and (max-width: 420px) {
  .star__img img {
    -webkit-transform: translate3d(0%, 39%, 0) scale(1.5);
    transform: translate3d(0%, 39%, 0) scale(1.5);
  }
}
.layer {
  width: 100%;
  height: 100%;
}
.fp-tableCell {
  position: relative;
}
.meta {
  padding-top: 7.2rem;
  position: relative;
}
.meta__back {
  width: 100%;
  height: 70rem;
  background: #f2f4f5;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -100;
}
@media screen and (max-width: 800px) {
  .meta__back {
    height: 54rem;
  }
}
@media screen and (max-width: 420px) {
  .meta__back {
    height: 45rem;
  }
}
.meta__text-wrap {
  padding: 0 8.58333% 0;
}
@media screen and (max-width: 420px) {
  .meta__text-wrap {
    padding: 0 7.5% 0;
  }
}
.meta__text {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  margin-bottom: 7.2rem;
}
@media screen and (max-width: 420px) {
  .meta__text {
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
  }
}
.meta__text li {
  margin-right: 6.4rem;
}
@media screen and (max-width: 420px) {
  .meta__text li {
    margin-right: 0;
    margin-bottom: 1.6rem;
  }
}
.meta__text li:last-child {
  margin-right: 0;
}
@media screen and (max-width: 420px) {
  .meta__text li:last-child {
    margin-bottom: 0;
  }
}
.meta__text .small-title {
  margin-bottom: 0.8rem;
}
@media screen and (max-width: 420px) {
  .meta__text .small-title {
    margin-bottom: 0.4rem;
  }
}
@media screen and (max-width: 420px) {
  .big-image {
    margin-top: 7.2rem;
    height: 50rem;
  }
}
.kamp {
  background: #f2f4f5;
  padding-top: 20rem;
  margin-top: 14.4rem;
}
@media screen and (max-width: 420px) {
  .kamp {
    padding-top: 7.2rem;
    margin-top: 7.2rem;
  }
}
.kamp ul {
  width: 76.666%;
  margin: 0 auto;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
}
.kamp li {
  width: 47.5543%;
}
.back-btn-wrap {
  text-align: center;
}
.back-btn {
  display: inline-block;
  font-size: 3.2rem;
  color: #020b16;
  letter-spacing: 0.2em;
  position: relative;
  -webkit-transition: 0.5s;
  -o-transition: 0.5s;
  transition: 0.5s;
  -webkit-transform: translate3d(44px, 0, 0);
  transform: translate3d(44px, 0, 0);
}
@media screen and (max-width: 420px) {
  .back-btn {
    font-size: 1.6rem;
    -webkit-transform: translate3d(22px, 0, 0);
    transform: translate3d(22px, 0, 0);
  }
}
.back-btn:after {
  content: '';
  width: 64px;
  height: 2px;
  background: #020b16;
  position: absolute;
  top: 0;
  bottom: 0;
  left: -88px;
  margin: auto;
  -webkit-transition: 0.5s;
  -o-transition: 0.5s;
  transition: 0.5s;
}
@media screen and (max-width: 420px) {
  .back-btn:after {
    width: 32px;
    left: -44px;
  }
}
.back-btn:before {
  content: '';
  width: 24px;
  height: 1px;
  background: #020b16;
  position: absolute;
  top: 0;
  bottom: 0;
  left: -88px;
  margin: auto;
  -webkit-transition: 0.5s;
  -o-transition: 0.5s;
  transition: 0.5s;
}
@media screen and (max-width: 800px) {
  .back-btn:before {
    width: 12px;
    left: -44px;
    -webkit-transform: rotate(-45deg) translate3d(4px, -4px, 0);
    transform: rotate(-45deg) translate3d(4px, -4px, 0);
    display: none;
  }
}
.back-btn:hover {
  -webkit-transform: translate3d(0, 0, 0);
  transform: translate3d(0, 0, 0);
}
.back-btn:hover:after {
  width: 80px;
  left: -112px;
}
.back-btn:hover:before {
  left: -112px;
  -webkit-transform: rotate(-45deg) translate3d(2px, -8px, 0);
  transform: rotate(-45deg) translate3d(2px, -8px, 0);
}
.who__wrap {
  width: 48.333%;
}
@media screen and (max-width: 800px) {
  .who__wrap {
    width: 100%;
    margin-top: 7.2rem;
  }
}
@media screen and (max-width: 420px) {
  .who__wrap {
    margin-top: 4rem;
  }
}
.who__name {
  color: #072142;
  margin-bottom: 2.4rem;
}
@media screen and (max-width: 420px) {
  .who__name {
    margin-bottom: 1.6rem;
  }
}
.who__jp {
  font-size: 2.4rem;
  letter-spacing: 0.3em;
  font-weight: bold;
  margin-bottom: 0.4rem;
}
@media screen and (max-width: 420px) {
  .who__jp {
    font-size: 1.3rem;
  }
}
.who__en {
  font-size: 1.8rem;
  letter-spacing: 0.2em;
  font-family: 'futura_de';
  line-height: 1.3;
}
@media screen and (max-width: 420px) {
  .who__en {
    font-size: 1rem;
  }
}
.who__text {
  margin-bottom: 6.4rem;
}
@media screen and (max-width: 420px) {
  .who__text {
    margin-bottom: 3.2rem;
  }
}
.who__image {
  -webkit-box-shadow: 0px 63px 154px -20px rgba(7, 33, 66, 0.5);
  box-shadow: 0px 63px 154px -20px rgba(7, 33, 66, 0.5);
}
@media screen and (max-width: 420px) {
  .who__image {
    -webkit-box-shadow: 0px 33px 84px -20px rgba(7, 33, 66, 0.5);
    box-shadow: 0px 33px 84px -20px rgba(7, 33, 66, 0.5);
  }
}
.passion__list {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
}
@media screen and (max-width: 800px) {
  .passion__list {
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    -webkit-box-pack: start;
    -ms-flex-pack: start;
    justify-content: flex-start;
  }
}
.passion__item {
  width: 29.75%;
}
@media screen and (max-width: 800px) {
  .passion__item {
    width: 100%;
    margin-top: 6.4rem;
  }
  .passion__item:first-child {
    margin-top: 0;
  }
}
@media screen and (max-width: 420px) {
  .passion__item {
    margin-top: 3.2rem;
  }
}
.passion__image {
  width: 42.016%;
  margin: 0 auto 2.4rem;
}
@media screen and (max-width: 800px) {
  .passion__image {
    width: 24.429%;
  }
}
@media screen and (max-width: 420px) {
  .passion__image {
    margin-bottom: 1.6rem;
  }
}
.skill-set__flex {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
}
@media screen and (max-width: 800px) {
  .skill-set__flex {
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    -webkit-box-pack: start;
    -ms-flex-pack: start;
    justify-content: flex-start;
  }
}
.skill-set__list {
  width: 47%;
}
@media screen and (max-width: 800px) {
  .skill-set__list {
    width: 100%;
  }
  .skill-set__list:last-child {
    margin-top: 7.2rem;
  }
}
.skill-set__item {
  margin-top: 6.4rem;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}
.skill-set__item:first-child {
  margin-top: 0;
}
@media screen and (max-width: 420px) {
  .skill-set__item {
    margin-top: 3.2rem;
  }
}
.skill-set__icon {
  width: 10.6382%;
  -ms-flex-item-align: center;
  align-self: center;
}
.skill-set__detail {
  width: 85.1063%;
}
.skill-set__meta {
  margin-bottom: 0.8rem;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
}
.skill-set__name {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: end;
  -ms-flex-align: end;
  align-items: flex-end;
}
.skill-set__year {
  font-size: 1.4rem;
  line-height: 1.2;
  color: #c0c5ca;
  margin-left: 0.8rem;
  letter-spacing: 0.2em;
}
@media screen and (max-width: 420px) {
  .skill-set__year {
    font-size: 1rem;
  }
}
.skill-set__ratio {
  font-size: 1.6rem;
  line-height: 1.2;
  color: #072142;
}
@media screen and (max-width: 420px) {
  .skill-set__ratio {
    font-size: 1rem;
  }
}
.skill-set__high {
  color: #ff4d5a;
}
.skill-set__bar {
  width: 100%;
  height: 1.4rem;
  background: #fff;
  position: relative;
  border-radius: 10px;
  -webkit-box-shadow: 0 5px 15px 0 rgba(7, 33, 66, 0.15);
  box-shadow: 0 5px 15px 0 rgba(7, 33, 66, 0.15);
}
@media screen and (max-width: 420px) {
  .skill-set__bar {
    height: 0.7rem;
  }
}
.skill-set__bar:after {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  height: 100%;
  border-radius: 10px;
  width: 10%;
}
.skill-set__bar.p90:after {
  background-image: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#072142),
    color-stop(42%, #8c2b7a),
    to(#ff4d5a)
  );
  background-image: -webkit-linear-gradient(
    left,
    #072142,
    #8c2b7a 42%,
    #ff4d5a
  );
  background-image: -o-linear-gradient(left, #072142, #8c2b7a 42%, #ff4d5a);
  background-image: linear-gradient(to right, #072142, #8c2b7a 42%, #ff4d5a);
}
.skill-set__bar.p90.in:after {
  -webkit-animation: ratio90 1.5s forwards;
  animation: ratio90 1.5s forwards;
}
.skill-set__bar.p80:after {
  background-image: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#072142),
    color-stop(50%, #8c2b7a),
    to(#ff4d5a)
  );
  background-image: -webkit-linear-gradient(
    left,
    #072142,
    #8c2b7a 50%,
    #ff4d5a
  );
  background-image: -o-linear-gradient(left, #072142, #8c2b7a 50%, #ff4d5a);
  background-image: linear-gradient(to right, #072142, #8c2b7a 50%, #ff4d5a);
}
.skill-set__bar.p80.in:after {
  -webkit-animation: ratio80 1.5s forwards;
  animation: ratio80 1.5s forwards;
}
.skill-set__bar.p70:after {
  background-image: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#072142),
    color-stop(65%, #8c2b7a),
    to(#ff4d5a)
  );
  background-image: -webkit-linear-gradient(
    left,
    #072142,
    #8c2b7a 65%,
    #ff4d5a
  );
  background-image: -o-linear-gradient(left, #072142, #8c2b7a 65%, #ff4d5a);
  background-image: linear-gradient(to right, #072142, #8c2b7a 65%, #ff4d5a);
}
.skill-set__bar.p70.in:after {
  -webkit-animation: ratio70 1.5s forwards;
  animation: ratio70 1.5s forwards;
}
.skill-set__bar.p60:after {
  background-image: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#072142),
    color-stop(75%, #8c2b7a),
    to(#ff4d5a)
  );
  background-image: -webkit-linear-gradient(
    left,
    #072142,
    #8c2b7a 75%,
    #ff4d5a
  );
  background-image: -o-linear-gradient(left, #072142, #8c2b7a 75%, #ff4d5a);
  background-image: linear-gradient(to right, #072142, #8c2b7a 75%, #ff4d5a);
}
.skill-set__bar.p60.in:after {
  -webkit-animation: ratio60 1.5s forwards;
  animation: ratio60 1.5s forwards;
}
.skill-set__bar.p50:after {
  background-image: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#072142),
    color-stop(65%, #8c2b7a)
  );
  background-image: -webkit-linear-gradient(left, #072142, #8c2b7a 65%);
  background-image: -o-linear-gradient(left, #072142, #8c2b7a 65%);
  background-image: linear-gradient(to right, #072142, #8c2b7a 65%);
}
.skill-set__bar.p50.in:after {
  -webkit-animation: ratio50 1.5s forwards;
  animation: ratio50 1.5s forwards;
}
.skill-set__bar.p40:after {
  background-image: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#072142),
    color-stop(65%, #8c2b7a)
  );
  background-image: -webkit-linear-gradient(left, #072142, #8c2b7a 65%);
  background-image: -o-linear-gradient(left, #072142, #8c2b7a 65%);
  background-image: linear-gradient(to right, #072142, #8c2b7a 65%);
}
.skill-set__bar.p40.in:after {
  -webkit-animation: ratio40 1.5s forwards;
  animation: ratio40 1.5s forwards;
}
.footer {
  width: 100%;
  padding: 14.4rem 0;
  text-align: center;
  background-image: -webkit-linear-gradient(
    349deg,
    #072142,
    #8c2b7a 52%,
    #ff4d5a
  );
  background-image: -o-linear-gradient(349deg, #072142, #8c2b7a 52%, #ff4d5a);
  background-image: linear-gradient(101deg, #072142, #8c2b7a 52%, #ff4d5a);
  position: relative;
  z-index: 100;
}
@media screen and (max-width: 420px) {
  .footer {
    padding: 7.2rem 0;
  }
}
.footer a {
  display: block;
  font-size: 2.8rem;
  line-height: 1.3;
  color: #fff;
  letter-spacing: 0.2em;
  -webkit-transition: 0.3s;
  -o-transition: 0.3s;
  transition: 0.3s;
}
@media screen and (max-width: 420px) {
  .footer a {
    font-size: 1.2rem;
  }
}
.footer a:first-child {
  margin-bottom: 2.4rem;
}
@media screen and (max-width: 420px) {
  .footer a:first-child {
    margin-bottom: 0.8rem;
  }
}
.footer a:hover {
  opacity: 0.5;
}
@-webkit-keyframes ratio90 {
  0% {
    width: 10%;
  }
  to {
    width: 90%;
  }
}
@keyframes ratio90 {
  0% {
    width: 10%;
  }
  to {
    width: 90%;
  }
}
@-webkit-keyframes ratio80 {
  0% {
    width: 10%;
  }
  to {
    width: 80%;
  }
}
@keyframes ratio80 {
  0% {
    width: 10%;
  }
  to {
    width: 80%;
  }
}
@-webkit-keyframes ratio70 {
  0% {
    width: 10%;
  }
  to {
    width: 70%;
  }
}
@keyframes ratio70 {
  0% {
    width: 10%;
  }
  to {
    width: 70%;
  }
}
@-webkit-keyframes ratio60 {
  0% {
    width: 10%;
  }
  to {
    width: 60%;
  }
}
@keyframes ratio60 {
  0% {
    width: 10%;
  }
  to {
    width: 60%;
  }
}
@-webkit-keyframes ratio50 {
  0% {
    width: 10%;
  }
  to {
    width: 50%;
  }
}
@keyframes ratio50 {
  0% {
    width: 10%;
  }
  to {
    width: 50%;
  }
}
@-webkit-keyframes ratio40 {
  0% {
    width: 10%;
  }
  to {
    width: 40%;
  }
}
@keyframes ratio40 {
  0% {
    width: 10%;
  }
  to {
    width: 40%;
  }
}
</style>
