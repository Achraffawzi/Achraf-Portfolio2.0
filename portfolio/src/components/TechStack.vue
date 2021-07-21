<template>
  <div class="tech-stack" id="tech-stack">
    <div class="container">
      <h2 class="stack__heading text-uppercase">tech stack</h2>
      <div
        class="container stack__icons text-center tech-stack-icons-container"
      >
        <i class="devicon-html5-plain-wordmark"></i>
        <i class="devicon-css3-plain-wordmark"></i>
        <i class="devicon-bootstrap-plain-wordmark"></i>
        <i class="devicon-sass-original"></i>
        <i class="devicon-javascript-plain"></i>
        <i class="devicon-vuejs-plain-wordmark"></i>
        <i class="devicon-csharp-plain-wordmark"></i>
        <i class="devicon-microsoftsqlserver-plain-wordmark"></i>
        <i class="devicon-git-plain-wordmark"></i>
        <i class="devicon-github-original-wordmark"></i>
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
  margin-top: 100px;

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

  .tech-stack-icons-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    row-gap: 30px;
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

@media screen and (max-width: 290px) {
  .tech-stack-icons-container {
    grid-template-columns: 1fr;
  }
}
</style>
