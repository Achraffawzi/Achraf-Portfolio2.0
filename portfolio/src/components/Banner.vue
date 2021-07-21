<template>
  <div class="banner" id="banner">
    <div class="container">
      <vue-particles
        color="#dedede"
        :particlesNumber="80"
        class="intro"
      ></vue-particles>
      <!-- links -->
      <!-- <input type="checkbox" id="nav-toggle"> -->
      <ul class="banner__ul mt-3 d-flex align-items-center list-unstyled">
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
      <label for="nav-toggle" class="icon-burger" @click="toggleNavbar">
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
      </label>
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
    </div>
  </div>
</template>

<script>
export default {
  name: "Banner",
  data() {
    return {
      collapsed: false,
    };
  },
  methods: {
    toggleNavbar() {
      let navbar = document.querySelector(".banner__ul");
      let lines = document.querySelectorAll(".line");

      if (this.collapsed) {
        lines[0].setAttribute(
          "style",
          "width: 30px;height: 5px; background: #fff;margin: 5px; transition: all 0.3s ease-in-out;"
        );
        lines[1].setAttribute(
          "style",
          "width: 30px;height: 5px; background: #fff;margin: 5px; transition: all 0.3s ease-in-out;"
        );
        lines[2].setAttribute(
          "style",
          "width: 30px;height: 5px; background: #fff;margin: 5px; transition: all 0.3s ease-in-out;"
        );
        navbar.style.bottom = "100%";

        this.collapsed = false;
      } else {
        lines[0].style.transform = "translateY(10px) rotate(225deg)";
        lines[1].setAttribute(
          "style",
          "opacity:0; -moz-opacity:0; filter:alpha(opacity=0)"
        );
        lines[2].style.transform = "translateY(-10px) rotate(-225deg)";

        navbar.style.bottom = "0";
        this.collapsed = true;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/home/variables.scss";
.banner {
  min-height: 100vh;
  position: relative;
  overflow: hidden;

  .intro {
    background: transparent;
    background-position: center center;
    background-repeat: no-repeat;
    background-size: cover;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -99999;
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
    z-index: -99;
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
    z-index: -99;
  }

  #nav-toggle {
    position: absolute;
    top: -900px;
  }

  // navbar toggle
  .icon-burger {
    display: none;
    position: fixed;
    right: 2%;
    top: 3%;
    z-index: 99;
    cursor: pointer;

    .line {
      width: 30px;
      height: 5px;
      background: #fff;
      margin: 5px;
      transition: all 0.3s ease-in-out;
    }
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
    margin-top: 30px;

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

@media screen and (max-width: 500px) {
  .icon-burger {
    display: block !important;
  }

  .banner__ul {
    // display: none !important;
    // background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7), #252837);
    background-color: $lighter-bg;
    position: fixed;
    top: 0%;
    left: 0;
    right: 0;
    bottom: 100%;
    width: auto;
    height: auto;
    z-index: 3;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    text-align: center;
    overflow: hidden;
    transition: all 0.5s ease-in-out;
    margin-top: 0 !important;

    .banner__anchor {
      margin: 0;
    }
  }

  .icon-burger:focus .banner__ul {
    bottom: 0;
  }

  :checked ~ .icon-burger .line:nth-child(1) {
    transform: translateY(10px) rotate(225deg);
  }
  :checked ~ .icon-burger .line:nth-child(3) {
    transform: translateY(-10px) rotate(-225deg);
  }
  :checked ~ .icon-burger .line:nth-child(2) {
    opacity: 0;
  }
}

@media screen and (max-width: 290px) {
  .banner {
    text-align: center;

    .banner__intro {
      margin-top: 120px;
    }
  }
  .intro__buttons {

    a {
      display: block;

      &:first-of-type {
        margin-right: 0px !important;
        margin-bottom: 10px;
      }
    }
  }
}
</style>
