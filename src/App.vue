<template>
  <div class="wrap">
    <div class="header" id="header">
      <div class="h-left">
        <p>Portfolio</p>
      </div>
      <div class="h-right">
        <div
          class="menu"
          :class="{ active: sidebar_modal == 1 }"
          @click="sidebar_mOnOff"
        >
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
    </div>
    <div class="contents">
      <div class="contents-home" id="home">
        <div class="home-title">
          <p id="home-title">Daeho Kim <br /></p>
          <p id="home-subtitle">Front-end Developer</p>
        </div>
        <div class="home-scroll" id="home-scroll">
          Scroll
          <span class="home-scroll-arrow updown">↓</span>
        </div>
      </div>
      <div class="contents-about" id="about">
        <div class="about-img" alt="" id="about-img" />
        <div class="about-introduce1" id="about-intro1">
          좌절에서 열정으로, 변곡점의 필요
        </div>
        <div class="about-introduce2" id="about-intro2">
          스스로 발전하는 단단한 인물이 돼야겠다는 다짐
        </div>
        <div class="about-introduce3" id="about-intro3">
          즉각적인 결과 도출, 표현의 다양성, 창의성, 짜임새
        </div>
        <div class="about-introduce4" id="about-intro4">
          비록 작은 프로젝트이지만 진행하면서 저 자신을 열정으로 가득 차게 해준
          것 같습니다
        </div>
        <div class="about-introduce5" id="about-intro5">
          신입 프론트엔드 김대호입니다
        </div>
      </div>
      <div class="contents-creative" id="creative">
        <p class="pj" id="pj-first">Creatives</p>
        <div class="creative-1">
          <p class="pj1-name" id="pj1-name">Whattodo</p>
          <div class="pj1-1" id="pj1-1" alt=""></div>
          <p class="pj1-exp1" id="pj1-exp1">처음으로 만든 Todo앱 입니다</p>
          <p class="pj1-exp2" id="pj1-exp2">
            프로필과 알람을 통해 다양한 일정을 정리할 수 있습니다
          </p>
          <p class="pj1-stack" id="pj1-stack">
            Stack - html / css / vue.js / mongodb / express.js / aws
          </p>
          <a
            class="creative-btn1"
            id="creative-btn1"
            href="https://github.com/daechu5657/Whattodo"
            target="_blank"
            >Source</a
          >
          <a
            class="creative-btn2"
            id="creative-btn2"
            href="http://whattodo-env.eba-fk3kewkc.us-west-2.elasticbeanstalk.com/"
            target="_blank"
            >View</a
          >
        </div>
        <div class="creative-2">
          <p class="pj2-name" id="pj2-name">Notwait</p>
          <div class="pj2-1" id="pj2-1" alt=""></div>
          <p class="pj2-exp1" id="pj2-exp1">
            매장에서의 주문관리 및 고객관리 앱입니다.
          </p>
          <p class="pj2-exp2" id="pj2-exp2">
            각 테이블의 qr코드를 통해 접속하여 사람과 대면하지 않고 주문 및
            소통이 가능하게끔 제작하였습니다.
          </p>
          <p class="pj2-stack" id="pj2-stack">
            Stack - html / css / vue.js / mongodb / express.js / aws
          </p>
          <a
            class="creative-btn1"
            id="creative-btn2-1"
            target="_blank"
            href="https://github.com/daechu5657/NotWait"
            >Source</a
          >
          <a
            class="creative-btn2-2"
            id="creative-btn2-2"
            target="_blank"
            href="http://notwait-env.eba-rczh4hhb.us-west-2.elasticbeanstalk.com/owner"
            >View Owner
            <p>CODE:1234</p></a
          >
          <a
            class="creative-btn2-3"
            id="creative-btn2-3"
            target="_blank"
            href="http://notwait-env.eba-rczh4hhb.us-west-2.elasticbeanstalk.com/customer/1"
            >View Customer
            <p>크롬 모바일 기기모드에서 원활한 이용 가능합니다</p></a
          >
        </div>
        <div class="creative-3">
          <p class="pj3-name" id="pj3-name">Notwait - web publishing</p>
          <div class="pj3-1" id="pj3-1" alt=""></div>
          <p class="pj3-exp1" id="pj3-exp1">Dalhamin</p>
          <p class="pj3-exp2" id="pj3-exp2">
            '달하민'이라는 실제 카페의 브랜드 웹을 제작하였습니다. mobile 버전
            (제작중)
          </p>
          <p class="pj3-stack" id="pj3-stack">Stack - html / css / vue.js</p>
          <a
            class="creative-btn1"
            id="creative-btn3-1"
            href="https://github.com/daechu5657/Dalhamin"
            target="_blank"
            >Source</a
          >
          <a
            class="creative-btn2"
            id="creative-btn3-2"
            href="https://daechu5657.github.io/Dalhamin/"
            target="_blank"
            >View</a
          >
        </div>
      </div>
      <div class="contents-contact" id="contact"></div>
    </div>
    <transition name="sidebar">
      <div class="sidebar" v-if="sidebar_modal == 1">
        <div class="profile">
          <div class="profile-img" src="./assets/man.jpg" />
          <p>김대호</p>
          <p>Tel : 010-8348-0031</p>
          <p>Email : kng02068@naver.com</p>
          <a href="https://github.com/daechu5657" target="_blank">Github</a>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {},
  methods: {
    sidebar_mOnOff() {
      if (this.sidebar_modal == 0) {
        this.sidebar_modal = 1;
      } else {
        this.sidebar_modal = 0;
      }
    },
    scroll() {
      var Element = document.documentElement.scrollTop;
      this.scrollv = Element;
      let vh = window.innerHeight;
      this.vh = vh;
      this.length = window.pageYOffset / this.vh;
    },
  },
  data() {
    return {
      sidebar_modal: 0,
      length: 0,
      vh: 0,
    };
  },
  computed: {},
  watch: {
    length(val) {
      console.log(val.toFixed(1));
      let len = val.toFixed(1);

      const home = document.querySelector('#home');
      const about_img = document.querySelector('#about-img');
      const about_intro1 = document.querySelector('#about-intro1');
      const about_intro2 = document.querySelector('#about-intro2');
      const about_intro3 = document.querySelector('#about-intro3');
      const about_intro4 = document.querySelector('#about-intro4');
      const about_intro5 = document.querySelector('#about-intro5');
      const creative = document.querySelector('#creative');
      const pj_first = document.querySelector('#pj-first');
      const pj1_name = document.querySelector('#pj1-name');
      const pj1_1 = document.querySelector('#pj1-1');
      const pj1_stack = document.querySelector('#pj1-stack');
      const pj1_exp1 = document.querySelector('#pj1-exp1');
      const pj1_exp2 = document.querySelector('#pj1-exp2');
      const creative_btn2 = document.querySelector('#creative-btn2');
      const creative_btn1 = document.querySelector('#creative-btn1');
      const pj2_name = document.querySelector('#pj2-name');
      const pj2_1 = document.querySelector('#pj2-1');
      const pj2_stack = document.querySelector('#pj2-stack');
      const pj2_exp1 = document.querySelector('#pj2-exp1');
      const pj2_exp2 = document.querySelector('#pj2-exp2');
      const creative_btn2_2 = document.querySelector('#creative-btn2-2');
      const creative_btn2_1 = document.querySelector('#creative-btn2-1');
      const creative_btn2_3 = document.querySelector('#creative-btn2-3');
      const pj3_name = document.querySelector('#pj3-name');
      const pj3_1 = document.querySelector('#pj3-1');
      const pj3_stack = document.querySelector('#pj3-stack');
      const pj3_exp1 = document.querySelector('#pj3-exp1');
      const pj3_exp2 = document.querySelector('#pj3-exp2');
      const creative_btn3_2 = document.querySelector('#creative-btn3-2');
      const creative_btn3_1 = document.querySelector('#creative-btn3-1');

      if (len >= 0) {
        home.style.opacity = `${1 - len}`;
        if (len >= 1.5 && len <= 2) {
          about_img.style.opacity = `${2 * (len - 1.5)}`;
          about_img.style.left = '42.5vw';
        } else if (len >= 2 && len <= 3) {
          about_img.style.left = `${35 - 10 * (len - 2)}vw`;
        } else if (len >= 3 && len <= 3.5) {
          about_intro1.style.opacity = `0`;
          about_intro2.style.opacity = `0`;
          about_intro3.style.opacity = `0`;
          about_intro4.style.opacity = `0`;
        } else if (len >= 3.5 && len <= 4.5) {
          about_intro1.style.opacity = `${len - 3.5}`;
          about_intro2.style.opacity = `${len - 3.5}`;
          about_intro3.style.opacity = `${len - 3.5}`;
          about_intro4.style.opacity = `${len - 3.5}`;
          about_intro1.style.top = `${35 + 5 * (len - 3.5)}vh`;
          about_intro2.style.left = `${55 - 5 * (len - 3.5)}vw`;
          about_intro3.style.left = `${55 - 5 * (len - 3.5)}vw`;
          about_intro4.style.top = `${63 - 5 * (len - 3.5)}vh`;
        } else if (len >= 5 && len <= 6) {
          about_intro1.style.opacity = `${2 * (6 - len)}`;
          about_intro2.style.opacity = `${2 * (6 - len)}`;
          about_intro3.style.opacity = `${2 * (6 - len)}`;
          about_intro4.style.opacity = `${2 * (6 - len)}`;
          about_intro1.style.top = `${40 - 5 * (len - 5)}vh`;
          about_intro2.style.left = `${50 + 5 * (len - 5)}vw`;
          about_intro3.style.left = `${50 + 5 * (len - 5)}vw`;
          about_intro4.style.top = `${58 + 5 * (len - 5)}vh`;
          about_intro5.style.opacity = `0`;
          about_img.style.left = `25vw`;
        } else if (len >= 6 && len <= 7) {
          about_intro5.style.opacity = `${len - 6}`;
          about_intro5.style.top = `${65 - 5 * (len - 6)}vh`;
          about_img.style.left = `${25 + 17.5 * (len - 6)}vw`;
        } else if (len >= 7.5 && len <= 8.5) {
          about_img.style.opacity = `${8.5 - len}`;
          about_intro5.style.opacity = `${8.5 - len}`;
        } else if (len >= 9 && len <= 10) {
          creative.style.height = `${100 * (len - 9)}vh`;
          creative.style.width = `${100 * (len - 9)}vw`;
          creative.style.left = `${50 - 50 * (len - 9)}vw`;
          creative.style.top = `${50 - 50 * (len - 9)}vh`;
          creative.style.borderRadius = `${50 - 50 * (len - 9)}%`;
          pj_first.style.opacity = '0';
        } else if (len >= 10.5 && len <= 11) {
          pj_first.style.opacity = `${2 * (len - 10.5)}`;
        } else if (len >= 11 && len <= 11.5) {
          pj_first.style.opacity = `${2 * (11.5 - len)}`;
          pj1_name.style.opacity = '0';
        } else if (len >= 11.5 && len <= 12) {
          pj1_name.style.opacity = `${2 * (len - 11.5)}`;
          pj1_name.style.left = `45vw`;
          pj1_name.style.top = `45vh`;
        } else if (len >= 12 && len <= 12.5) {
          pj1_name.style.left = `${45 - 70 * (len - 12)}vw`;
          pj1_name.style.top = `${45 - 60 * (len - 12)}vh`;
          pj1_1.style.opacity = `0`;
          pj1_stack.style.opacity = `0`;
          pj1_exp1.style.opacity = `0`;
          pj1_exp2.style.opacity = `0`;
          creative_btn1.style.opacity = '0';
          creative_btn2.style.opacity = '0';
        } else if (len >= 12.5 && len <= 13) {
          pj1_1.style.left = `${10 + 10 * (len - 12.5)}vw`;
          pj1_1.style.opacity = `${2 * (len - 12.5)}`;
          pj1_stack.style.top = `${74 - 8 * (len - 12.5)}vh`;
          pj1_stack.style.opacity = `${2 * (len - 12.5)}`;
          pj1_exp1.style.top = `${23 + 8 * (len - 12.5)}vh`;
          pj1_exp1.style.opacity = `${2 * (len - 12.5)}`;
          pj1_exp2.style.left = `${54 - 8 * (len - 12.5)}vw`;
          pj1_exp2.style.opacity = `${2 * (len - 12.5)}`;
          creative_btn1.style.opacity = `${2 * (len - 12.5)}`;
          creative_btn2.style.opacity = `${2 * (len - 12.5)}`;
          creative_btn1.style.top = `${68 - 8 * (len - 12.5)}vh`;
          creative_btn2.style.top = `${68 - 8 * (len - 12.5)}vh`;
        } else if (len >= 14 && len <= 14.5) {
          pj1_1.style.opacity = `${2 * (14.5 - len)}`;
          pj1_name.style.opacity = `${2 * (14.5 - len)}`;
          pj1_stack.style.opacity = `${2 * (14.5 - len)}`;
          pj1_exp1.style.opacity = `${2 * (14.5 - len)}`;
          pj1_exp2.style.opacity = `${2 * (14.5 - len)}`;
          creative_btn1.style.opacity = `${2 * (14.5 - len)}`;
          creative_btn2.style.opacity = `${2 * (14.5 - len)}`;
          pj2_name.style.opacity = `0`;
          pj2_1.style.opacity = `0`;
          pj2_stack.style.opacity = `0`;
          pj2_exp1.style.opacity = `0`;
          pj2_exp2.style.opacity = `0`;
          creative_btn2_1.style.opacity = '0';
          creative_btn2_2.style.opacity = '0';
          creative_btn2_3.style.opacity = '0';
        } else if (len >= 15 && len <= 15.5) {
          pj2_name.style.opacity = `${2 * (len - 15)}`;
          pj2_1.style.left = `${10 + 10 * (len - 15)}vw`;
          pj2_1.style.opacity = `${2 * (len - 15)}`;
          pj2_stack.style.top = `${74 - 8 * (len - 15)}vh`;
          pj2_stack.style.opacity = `${2 * (len - 15)}`;
          pj2_exp1.style.top = `${23 + 8 * (len - 15)}vh`;
          pj2_exp1.style.opacity = `${2 * (len - 15)}`;
          pj2_exp2.style.left = `${54 - 8 * (len - 15)}vw`;
          pj2_exp2.style.opacity = `${2 * (len - 15)}`;
          creative_btn2_1.style.opacity = `${2 * (len - 15)}`;
          creative_btn2_2.style.opacity = `${2 * (len - 15)}`;
          creative_btn2_3.style.opacity = `${2 * (len - 15)}`;
          creative_btn2_1.style.top = `${68 - 8 * (len - 15)}vh`;
          creative_btn2_2.style.top = `${68 - 8 * (len - 15)}vh`;
          creative_btn2_3.style.top = `${68 - 8 * (len - 15)}vh`;
        } else if (len >= 16.5 && len <= 17) {
          pj2_1.style.opacity = `${2 * (17 - len)}`;
          pj2_name.style.opacity = `${2 * (17 - len)}`;
          pj2_stack.style.opacity = `${2 * (17 - len)}`;
          pj2_exp1.style.opacity = `${2 * (17 - len)}`;
          pj2_exp2.style.opacity = `${2 * (17 - len)}`;
          creative_btn2_1.style.opacity = `${2 * (17 - len)}`;
          creative_btn2_2.style.opacity = `${2 * (17 - len)}`;
          creative_btn2_3.style.opacity = `${2 * (17 - len)}`;
          pj3_name.style.opacity = `0`;
          pj3_1.style.opacity = `0`;
          pj3_stack.style.opacity = `0`;
          pj3_exp1.style.opacity = `0`;
          pj3_exp2.style.opacity = `0`;
          creative_btn3_1.style.opacity = '0';
          creative_btn3_2.style.opacity = '0';
        } else if (len >= 17.5 && len <= 18) {
          pj3_name.style.opacity = `${2 * (len - 17.5)}`;
          pj3_1.style.left = `${10 + 10 * (len - 17.5)}vw`;
          pj3_1.style.opacity = `${2 * (len - 17.5)}`;
          pj3_stack.style.top = `${74 - 8 * (len - 17.5)}vh`;
          pj3_stack.style.opacity = `${2 * (len - 17.5)}`;
          pj3_exp1.style.top = `${23 + 8 * (len - 17.5)}vh`;
          pj3_exp1.style.opacity = `${2 * (len - 17.5)}`;
          pj3_exp2.style.left = `${54 - 8 * (len - 17.5)}vw`;
          pj3_exp2.style.opacity = `${2 * (len - 17.5)}`;
          creative_btn3_1.style.opacity = `${2 * (len - 17.5)}`;
          creative_btn3_2.style.opacity = `${2 * (len - 17.5)}`;
          creative_btn3_2.style.top = `${68 - 8 * (len - 17.5)}vh`;
          creative_btn3_1.style.top = `${68 - 8 * (len - 17.5)}vh`;
        }
      }
    },
  },
  mounted() {
    window.onbeforeunload = function () {
      window.scrollTo(0, 0);
    };
    window.addEventListener('scroll', this.scroll);
    document.getElementById('home-title').classList.add('fadeinUD');
    document.getElementById('home-subtitle').classList.add('fadeLR');
    document.getElementById('header').classList.add('opacity');

    setTimeout(() => {
      document.getElementById('home-scroll').classList.add('fadeinDU');
    }, 1000);
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Staatliches&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Do+Hyeon&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Questrial&display=swap');
@import url(https://cdn.jsdelivr.net/gh/moonspam/NanumSquare@1.0/nanumsquare.css);
* {
  margin: 0;
  padding: 0;
  /* font-family: 'Staatliches', cursive; */
  /* font-family: 'NanumSquare', san-serif; */
}
a {
  text-decoration: none;
}
div {
  box-sizing: border-box;
}
body {
  margin: 0;
  padding: 0;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  overflow-x: hidden;
}
body::-webkit-scrollbar {
  display: none;
}
.wrap {
  width: 100vw;
  height: 1900vh;
  background-color: #161616;
  max-width: 100%;
}
.header {
  position: fixed;
  width: 100vw;
  height: 7vh;
  font-family: 'Staatliches', cursive;
  color: #f5f5f5;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  background-color: transparent;
  z-index: 100;
}
.h-left {
  position: relative;
  width: 10vw;
  font-size: 2vw;
  text-align: left;
  padding-left: 1vw;
}
.h-right {
  position: relative;
  width: 10vw;
  text-align: right;
  font-size: 1.2vw;
  color: #f5f5f5;
  padding-right: 1vw;
}
.menu {
  position: relative;
  width: 1.5vw;
  height: 2vh;
  left: 7.5vw;
  transition: all 0.3s cubic-bezier(0.455, 0.03, 0.515, 0.955);
}
.menu span {
  position: absolute;
  left: 0;
  width: 100%;
  height: 4px;
  background-color: #fff;
  border-radius: 2px;
  transition: all 0.3s cubic-bezier(0.455, 0.03, 0.515, 0.955);
}
.menu span:nth-of-type(1) {
  top: 0;
}

.menu span:nth-of-type(2) {
  top: 1vh;
}

.menu span:nth-of-type(3) {
  top: 2vh;
}
.menu.active span:nth-of-type(1) {
  -webkit-transform: translateY (1vh) rotate (-45deg);
  transform: translateY(1vh) rotate(-45deg);
}

.menu.active span:nth-of-type(2) {
  opacity: 0;
}

.menu.active span:nth-of-type(3) {
  -webkit-transform: translateY(-1vh) rotate(45deg);
  transform: translateY(-1vh) rotate(45deg);
}
.sidebar {
  position: fixed;
  width: 15vw;
  height: 100vh;
  background-color: #75757524;
  right: 0;
  top: 0;
  backdrop-filter: blur(5px);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  z-index: 10;
}
.sidebar-enter-active {
  animation: sidebar 0.3s cubic-bezier(0.455, 0.03, 0.515, 0.955);
}
.sidebar-leave-active {
  animation: sidebar 0.3s cubic-bezier(0.455, 0.03, 0.515, 0.955) reverse;
}
@keyframes sidebar {
  0% {
    opacity: 0;
    transform: translatex(15vw);
  }
  100% {
    opacity: 1;
    transform: translatex(0vw);
  }
}
.profile {
  position: relative;
  width: 14vw;
  height: 80vh;
  left: 0.5vw;
  top: 9vh;
  font-family: 'Staatliches', cursive;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.profile > p {
  font-size: 1vw;
  padding: 10px 0;
  color: #f5f5f5;
}
.profile > a {
  font-size: 1vw;
  padding: 10px 0;
  color: #f5f5f5;
}
.profile > p:nth-child(2) {
  font-family: 'NanumSquare', san-serif;
  font-weight: 900;
  padding: 20px 0;
}
.profile-img {
  width: 10vw;
  height: 10vw;
  border-radius: 50%;
  background-image: url('./assets/man.jpg');
  background-size: 108%;
  background-position-y: -2vh;
  background-position-x: -0.4vw;
  background-repeat: no-repeat;
}
.sidebar-bottom {
  position: relative;
  width: 14vw;
  height: 10vh;
  left: 0.5vw;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}
.contents {
  position: relative;
  width: 100vw;
  height: 1900vh;
  background-color: transparent;
}
.contents-home {
  position: fixed;
  width: 100vw;
  height: 100vh;
  background-attachment: fixed;
  transition: 1s ease;
  font-family: 'NanumSquare', san-serif;
}
.home-title {
  position: relative;
  color: #f5f5f5;
  top: 46.5vh;
  text-align: center;
  line-height: 6.5vh;
  transition: 1s ease;
}
#home-title {
  position: relative;
  color: #f5f5f5;
  font-size: 3vw;
  text-align: center;
  transition: 1s ease;
  top: 0;
}
#home-subtitle {
  position: relative;
  font-size: 1.5vw;
  transition: 1s ease;
  left: 0;
}
.home-scroll {
  color: #f5f5f5;
  font-size: 1vw;
  position: relative;
  top: 83vh;
  display: flex;
  flex-direction: row;
  justify-content: center;
  opacity: 0;
}
.home-scroll-arrow {
  position: relative;
  left: 0.5vw;
}
.contents-about {
  position: fixed;
  width: 100vw;
  height: 100vh;
  background-attachment: fixed;
  transition: 1s ease;
  font-family: 'NanumSquare', san-serif;
  font-weight: 600;
}
.about-img {
  position: absolute;
  width: 15vw;
  height: 30vh;
  border-radius: 50%;
  top: 35vh;
  left: 42.5vw;
  opacity: 0;
  transition: 1s ease;
  background-image: url('./assets/man.jpg');
  background-size: 107%;
  background-position-y: -2vh;
  background-position-x: -0.5vw;
  background-repeat: no-repeat;
}
.contents-about > div {
  position: absolute;
  color: #f5f5f5;
  opacity: 0;
  transition: 1s ease;
}
.about-name {
  left: 25vw;
  top: 65vh;
  font-size: 1.5vw;
  width: 15vw;
  text-align: center;
  line-height: 10vw;
}
.about-introduce1 {
  left: 50vw;
  top: 35vh;
  font-size: 1.2vw;
  width: 18vw;
}
.about-introduce2 {
  left: 55vw;
  top: 46vh;
  font-size: 1.2vw;
  width: 24vw;
}
.about-introduce3 {
  left: 55vw;
  top: 52vh;
  font-size: 1.2vw;
  width: 26vw;
}
.about-introduce4 {
  left: 50vw;
  top: 63vh;
  font-size: 1.2vw;
}
.about-introduce5 {
  left: 30vw;
  top: 65vh;
  font-size: 2vw;
  width: 40vw;
  line-height: 10vw;
  text-align: center;
}

.contents-creative {
  position: fixed;
  width: 0vw;
  height: 0vh;
  top: 50vh;
  left: 50vw;
  background-attachment: fixed;
  background-color: #0e0e0e;
  transition: 1s ease;
  border-radius: 50%;
  font-family: 'NanumSquare', san-serif;
}
.pj {
  color: #fcfcfc;
  font-size: 1.5vw;
  position: fixed;
  width: 10vw;
  height: 10vh;
  line-height: 10vh;
  text-align: center;
  left: 45vw;
  top: 45vh;
  opacity: 0;
  transition: 1s ease;
  font-family: 'Staatliches', cursive;
}
.pj1-name {
  color: #fcfcfc;
  font-size: 1.5vw;
  position: fixed;
  width: 10vw;
  height: 10vh;
  line-height: 10vh;
  text-align: center;
  left: 45vw;
  top: 45vh;
  opacity: 0;
  transition: 1s ease;
  font-family: 'Staatliches', cursive;
}
.pj1-1 {
  width: 20vw;
  height: 45vh;
  border-radius: 50px;
  position: absolute;
  left: 10vw;
  top: 30vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
  background-image: url('./assets/project1-1.png');
  background-repeat: no-repeat;
  background-position-x: 48%;
  background-position-y: 0%;
  background-size: 134%;
}
.pj1-stack {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 25vw;
  height: 10vh;
  line-height: 10vh;
  top: 74vh;
  left: 50vw;
  text-align: left;
  opacity: 0;
  transition: 1s ease;
  font-family: 'Staatliches', cursive;
}
.pj1-exp1 {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 20vw;
  height: 10vh;
  text-align: left;
  line-height: 10vh;
  left: 50vw;
  top: 23vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
}
.pj1-exp2 {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 24vw;
  height: 10vh;
  text-align: left;
  line-height: 10vh;
  left: 54vw;
  top: 37vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
}
.creative-btn1 {
  color: #fcfcfc;
  font-size: 1vw;
  width: 4vw;
  height: 2vh;
  text-align: center;
  line-height: 2vh;
  position: absolute;
  left: 50vw;
  top: 68vh;
  transition: 1s ease;
  font-weight: 600;
  opacity: 0;
}
.creative-btn1:hover {
  color: #161616;
}
.creative-btn1::before {
  display: block;
  content: '';
  width: 4px;
  height: 100%;
  background-color: #fcfcfc;
  position: absolute;
  top: 0;
  transition: 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
  z-index: -1;
}
.creative-btn1:hover::before {
  width: 101%;
}
.creative-btn2 {
  color: #fcfcfc;
  font-size: 1vw;
  width: 4vw;
  height: 2vh;
  text-align: center;
  line-height: 2vh;
  position: absolute;
  left: 55vw;
  top: 68vh;
  transition: 1s ease;
  font-weight: 600;
  opacity: 0;
}
.creative-btn2:hover {
  color: #161616;
}
.creative-btn2::before {
  display: block;
  content: '';
  width: 4px;
  height: 100%;
  background-color: #fcfcfc;
  position: absolute;
  top: 0;
  transition: 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
  z-index: -1;
}
.creative-btn2:hover::before {
  width: 101%;
}
.creative-btn2-2 {
  color: #fcfcfc;
  font-size: 1vw;
  width: 8vw;
  text-align: center;
  line-height: 2vh;
  position: absolute;
  left: 55vw;
  top: 68vh;
  transition: 1s ease;
  font-weight: 600;
  opacity: 0;
}
.creative-btn2-2 > p {
  color: #0e0e0e;
}
.creative-btn2-2:hover {
  color: #161616;
}
.creative-btn2-2::before {
  display: block;
  content: '';
  width: 4px;
  height: 100%;
  background-color: #fcfcfc;
  position: absolute;
  top: 0;
  transition: 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
  z-index: -1;
}
.creative-btn2-2:hover::before {
  width: 101%;
}

.creative-btn2-3 {
  color: #fcfcfc;
  font-size: 1vw;
  width: 27vw;
  text-align: center;
  line-height: 2vh;
  position: absolute;
  left: 63vw;
  top: 68vh;
  transition: 1s ease;
  font-weight: 600;
  opacity: 0;
  display: flex;
  flex-direction: row;
}
.creative-btn2-3:hover {
  color: #161616;
}
.creative-btn2-3::before {
  display: block;
  content: '';
  width: 4px;
  height: 100%;
  background-color: #fcfcfc;
  position: absolute;
  top: 0;
  transition: 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
  z-index: -1;
}
.creative-btn2-3:hover::before {
  width: 101%;
}
.creative-btn2-3 > p {
  color: #0e0e0e;
}

.pj2-name {
  color: #fcfcfc;
  font-size: 1.5vw;
  position: fixed;
  width: 10vw;
  height: 10vh;
  line-height: 10vh;
  text-align: left;
  left: 10vw;
  top: 15vh;
  opacity: 0;
  transition: 1s ease;
  font-family: 'Staatliches', cursive;
}
.pj2-1 {
  width: 20vw;
  height: 45vh;
  border-radius: 50px;
  position: absolute;
  left: 10vw;
  top: 30vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
  background-image: url('./assets/project2-2.png');
  background-position-x: 50%;
  background-repeat: no-repeat;
}
.pj2-stack {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 25vw;
  height: 10vh;
  line-height: 10vh;
  top: 74vh;
  left: 50vw;
  text-align: left;
  opacity: 0;
  transition: 1s ease;
  font-family: 'Staatliches', cursive;
}
.pj2-exp1 {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 20vw;
  height: 10vh;
  text-align: left;
  line-height: 10vh;
  left: 50vw;
  top: 23vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
}
.pj2-exp2 {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 24vw;
  height: 10vh;
  text-align: left;
  line-height: 10vh;
  left: 54vw;
  top: 37vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
}

.pj3-name {
  color: #fcfcfc;
  font-size: 1.5vw;
  position: fixed;
  width: 30vw;
  height: 10vh;
  line-height: 10vh;
  text-align: left;
  left: 10vw;
  top: 15vh;
  opacity: 0;
  transition: 1s ease;
  font-family: 'Staatliches', cursive;
}
.pj3-1 {
  width: 20vw;
  height: 45vh;
  border-radius: 50px;
  position: absolute;
  left: 10vw;
  top: 30vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
  background-image: url('./assets/project3-1.png');
  background-position-x: 50%;
  background-repeat: no-repeat;
  background-size: 230%;
}
.pj3-stack {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 25vw;
  height: 10vh;
  line-height: 10vh;
  top: 74vh;
  left: 50vw;
  text-align: left;
  opacity: 0;
  transition: 1s ease;
  font-family: 'Staatliches', cursive;
}
.pj3-exp1 {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 20vw;
  height: 10vh;
  text-align: left;
  line-height: 10vh;
  left: 50vw;
  top: 23vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
}
.pj3-exp2 {
  font-size: 1vw;
  color: #fcfcfc;
  position: absolute;
  width: 25vw;
  height: 10vh;
  text-align: left;
  line-height: 10vh;
  left: 54vw;
  top: 37vh;
  opacity: 0;
  transition: 1s ease;
  font-weight: 600;
}
/* .contents-contact {
  position: relative;
  width: 100vw;
  height: 100vh;

  background-attachment: fixed;
} */

/* 효과 */
.updown {
  animation: updown 1s infinite ease-out;
}
.fadeLR {
  animation: fadeLR 2s cubic-bezier(0.215, 0.61, 0.355, 1);
}
.fadeRL {
  animation: fadeRL 2s cubic-bezier(0.215, 0.61, 0.355, 1);
}
.fadeinUD {
  animation: fadeinUD 2s cubic-bezier(0.215, 0.61, 0.355, 1);
}
.fadeinDU {
  animation: fadeinDU 2s cubic-bezier(0.215, 0.61, 0.355, 1) forwards;
}
.opacity {
  animation: opacity 2s cubic-bezier(0.215, 0.61, 0.355, 1);
}
@keyframes updown {
  0% {
    transform: translatey(0vh);
  }
  50% {
    transform: translatey(0.5vh);
  }
  100% {
    transform: translatey(0vh);
  }
}
@keyframes fadeLR {
  0% {
    opacity: 0;
    transform: translatex(-2vw);
  }
  50% {
    opacity: 0;
    transform: translatex(-2vw);
  }
  100% {
    opacity: 1;
    transform: translatex(0vw);
  }
}
@keyframes fadeRL {
  0% {
    opacity: 0;
    transform: translatex(2vw);
  }
  50% {
    opacity: 0;
    transform: translatex(2vw);
  }
  100% {
    opacity: 1;
    transform: translatex(0vw);
  }
}
@keyframes fadeinUD {
  0% {
    opacity: 0;
    transform: translatey(-2vh);
  }
  50% {
    opacity: 0;
    transform: translatey(-2vh);
  }
  100% {
    opacity: 1;
    transform: translatey(0vh);
  }
}
@keyframes fadeinDU {
  0% {
    opacity: 0;
    transform: translatey(2vh);
  }
  50% {
    opacity: 0;
    transform: translatey(2vh);
  }
  100% {
    opacity: 1;
    transform: translatey(0vh);
  }
}
@keyframes opacity {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
