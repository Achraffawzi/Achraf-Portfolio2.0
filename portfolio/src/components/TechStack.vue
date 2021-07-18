<template>
  <div class="tech-stack" id="tech-stack">
    <h2 class="stack__heading text-uppercase">tech stack</h2>
    <div class="container stack__icons text-center">
      <div class="row just-content-center flex-wrap">
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-html5-plain-wordmark"></i>
        </div>
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-css3-plain-wordmark"></i>
        </div>
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-bootstrap-plain-wordmark"></i>
        </div>
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-sass-original"></i>
        </div>
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-javascript-plain"></i>
        </div>
        <!--  -->
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-vuejs-plain-wordmark"></i>
        </div>
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-csharp-plain-wordmark"></i>
        </div>
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1 col-offset-md-4">
          <i class="devicon-microsoftsqlserver-plain-wordmark"></i>
        </div>
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-git-plain-wordmark"></i>
        </div>
        <div class="icons__col col-sm-6 col-md-4 col-lg-3 col-xl-1">
          <i class="devicon-github-original-wordmark"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TechStack",
};
</script>

<style lang="scss" scoped>
@import "../scss/home/variables.scss";
.tech-stack {
  margin-top: 150px;

  .stack__heading {
    position: relative;
    font-size: 25px;

    &:before {
      content: "";
      width: 50px;
      height: 6px;
      position: absolute;
      bottom: -10px;
      background-color: $white-color;
    }

    &:after {
      content: "";
      width: 140px;
      height: 1px;
      position: absolute;
      bottom: -8px;
      left: 20px;
      background-color: $white-color;
    }
  }

  .stack__icons {
    margin-top: 40px;

    .icons__col {
      margin: 0 30px 30px;
    }

    i[class^="devicon"] {
      font-size: 70px;
    }
  }
}
</style>
