<template>
  <div class="about" id="about">
    <div class="container">
      <h2 class="about__heading text-uppercase">about</h2>
    <p class="about__content">
      Web development has been my passion ever since I discovered it for the
      first time. As this passion grows, I started learning and getting in depth
      in web technologies and frameworks. Hard work, punctuality and quality of
      my work are the major caracteristics I put in in every project.
    </p>
    <a
      class="about__cv"
      href="https://drive.google.com/uc?export=download&id=1ZhhhpU2x5N2r9NNr2CpzTxOf5UBdBsGZ"
      >download CV</a
    >
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
};
</script>

<style lang="scss" scoped>
@import "../scss/home/variables.scss";
.about {
  margin-top: 30px;

  .about__heading {
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

  // about content
  .about__content {
    margin: 40px 0 20px;
    width: 800px;
    max-width: 90vw;
  }

  .about__cv {
    padding: 7px;
    border: 1px solid $white-color;
    color: $white-color;
    font-size: 14px;
    text-transform: uppercase;
    background-color: transparent;
    transition: background-color 0.2s linear, color 0.2s linear;

    &:hover {
      color: $darker-bg;
      background-color: $white-color;
    }
  }
}
</style>
