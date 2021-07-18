<template>
  <div class="footer">
    <!-- Social media -->
    <div class="footer__socialMedia">
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
    <!-- copyrights -->
    <p class="footer__copyrights mt-3">
      Designed &amp; Built by
      <a
        class="font-weight-bold footer__meHighlight"
        href="https://github.com/Achraffawzi"
        >Achraf FAWZI</a
      >
      &copy; {{ getCopyrightsDate }}
    </p>
  </div>
</template>

<script>
export default {
  name: "Footer",
  computed: {
    getCopyrightsDate() {
      return new Date().getFullYear();
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/home/variables.scss";
.footer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  // Social media
  .footer__socialMedia {
    display: flex;
    justify-content: center;
    align-items: center;

    .socialMedia__anchors {
      font-size: 20px;
      margin-right: 20px;
    }
  }

  .footer__meHighlight {
      color: $pinkish-color;
    }
}
</style>
