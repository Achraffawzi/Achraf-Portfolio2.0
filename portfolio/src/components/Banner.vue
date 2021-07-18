<template>
  <div class="banner" id="banner">
    <!-- links -->
    <ul class="d-flex align-items-center list-unstyled">
      <li>
        <a href="#banner" class="banner__anchor text-uppercase active ml-0"
          >home</a
        >
      </li>
      <li>
        <a href="#about" class="banner__anchor text-uppercase">about</a>
      </li>
      <li>
        <a href="#tech-stack" class="banner__anchor text-uppercase"
          >Tech stack</a
        >
      </li>
      <li>
        <a href="#projects" class="banner__anchor text-uppercase">projects</a>
      </li>
      <li>
        <a href="#contact" class="banner__anchor text-uppercase">contact</a>
      </li>
    </ul>
    <!-- profile picture -->
    <img
      src="../assets/me-black-bg.png"
      draggable="false"
      alt="Achraf FAWZI"
      class="banner__picture"
    />
    <!-- intro -->
    <div class="banner__intro">
      <div class="intro__name">I'm Achraf FAWZI</div>
      <div class="intro__title">Web developer</div>
      <div class="intro__buttons">
        <a href="#projects" class="intro__viewProjectsBtn">View my work</a>
        <a href="#contact" class="intro__contactBtn">contact me</a>
      </div>
    </div>
    <!-- Social media -->
    <div class="banner__socialMedia">
      <a
        href="https://www.linkedin.com/in/achraf-fawzi-dev/"
        class="socialMedia__anchors"
      >
        <i class="fab fa-linkedin-in"></i>
      </a>
      <a href="https://github.com/Achraffawzi" class="socialMedia__anchors">
        <i class="fab fa-github"></i>
      </a>
      <a href="mailto:achraf.fawzi.a@gmail.com" class="socialMedia__anchors">
        <i class="far fa-envelope"></i>
      </a>
      <a
        href="https://www.instagram.com/itsyealpha/"
        class="socialMedia__anchors"
      >
        <i class="fab fa-instagram"></i>
      </a>
    </div>
    <!-- The intro slideshow -->
    <div class="intro">
      <div class="intro-text">
        <div class="hide">
          <span class="text">Welcome everyone to</span>
        </div>
        <div class="hide">
          <span class="text">Achraf FAWZI's</span>
        </div>
        <div class="hide">
          <span class="text">Portfolio</span>
        </div>
      </div>
      <vue-particles
        color="#dedede"
        :particlesNumber="170"
        class="intro"
      ></vue-particles>
    </div>
    <div class="slider"></div>
  </div>
</template>

<script>
import gsap from "gsap";
// import particlesJS from "particles.js";
export default {
  name: "Banner",
  mounted() {
    // particleJS
    // particlesJS.load('particles-js', '../particlesjs-config.json');

    // GSAP Animation
    const tl = gsap.timeline({ defaults: { ease: "power1.out" } });
    tl.to(".text", { y: "0%", duration: 1, stagger: 0.25 });
    tl.to(".slider", { y: "-100%", duration: 1.5, delay: 0.5 });
    tl.to(".intro", { y: "-100%", duration: 1 }, "-=1");
    tl.fromTo("nav", { opacity: 0 }, { opacity: 1, duration: 1 });
    tl.fromTo(".big-text", { opacity: 0 }, { opacity: 1, duration: 1 }, "-=1");
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/home/variables.scss";
.banner {
  min-height: 100vh;
  position: relative;

  // Gsap animation
  .intro {
    // background: $lighter-bg;
    background-position: center center;
    background-repeat: no-repeat;
    background-size: cover;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 999;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    &-text {
      font-size: 3rem;
      font-weight: 600;
      font-weight: bold;
      letter-spacing: 4px;
    }

    .hide {
      background-color: transparent;
      overflow: hidden;
    }

    .hide span {
      display: inline-block;
      transform: translateY(100%);
    }
  }

  .slider {
    background-color: $pinkish-color;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 999;
    width: 100%;
    height: 100%;
    transform: translateY(100%);
  }

  &:after {
    content: "";
    width: 600px;
    height: 550px;
    border-radius: 50%;
    background: #000;
    position: absolute;
    right: -104px;
    top: -134px;
    z-index: -9999;
    box-shadow: -29px 0 29px 1px #404349;
  }

  &:before {
    content: "";
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background: linear-gradient(to right, #404349, #000);
    position: absolute;
    right: 400px;
    top: 400px;
    z-index: -9999;
  }

  // Profile picture
  .banner__picture {
    position: absolute;
    right: 110px;
    width: 220px;
    height: 260px;
    top: 50px;
  }

  // banner navbar styling
  .banner__anchor {
    margin: 0 15px;
    font-size: 14px;

    &.active {
      color: $pinkish-color;
    }

    &:hover {
      color: $pinkish-color;
    }
  }

  // Banner intro styling
  .banner__intro {
    text-transform: uppercase;
    margin-top: 200px;

    .intro__name {
      font-size: 40px;
      letter-spacing: 4px;
    }

    .intro__title {
      font-size: 18px;
      letter-spacing: 2px;
    }

    .intro__buttons {
      margin-top: 30px;

      .intro__viewProjectsBtn {
        font-weight: 500;
        padding: 7px;
        border: none;
        color: $white-color;
        text-transform: uppercase;
        background-color: $pinkish-color;
        margin-right: 10px;
      }

      .intro__contactBtn {
        font-weight: 500;
        padding: 7px;
        border: 1px solid $white-color;
        color: $white-color;
        text-transform: uppercase;
        background-color: transparent;
        transition: background-color 0.2s linear, color 0.2s linear;

        &:hover {
          color: $darker-bg;
          background-color: $white-color;
        }
      }
    }
  }

  // Social media
  .banner__socialMedia {
    position: absolute;
    bottom: 5%;
    right: 0;

    .socialMedia__anchors {
      font-size: 20px;
      margin-right: 20px;
    }
  }
}

// Media query
@media screen and (max-width: 785px) {
  .banner {
    &:after {
      content: "";
      background: linear-gradient(to right, $lighter-bg, $darker-bg);
      position: absolute;
      right: -200px;
      top: -134px;
      box-shadow: -29px 0 29px 1px #404349;
    }

    &:before {
      content: "";
      width: 100px;
      height: 100px;
      border-radius: 50%;
      background: linear-gradient(to left, #404349, $lighter-bg);
      position: absolute;
      right: 400px;
      top: 400px;
      z-index: -9999;
    }
  }
  .banner__picture {
    display: none;
  }
}

@media screen and (max-width: 540px) { 
.banner {

    &:before {
      content: "";
      width: 100px;
      height: 100px;
      border-radius: 50%;
      background: linear-gradient(to left, #404349, $lighter-bg);
      position: absolute;
      right: 300px;
      top: 400px;
      z-index: -9999;
    }
  }
}
</style>
