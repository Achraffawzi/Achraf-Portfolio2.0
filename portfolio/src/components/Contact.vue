<template>
  <div class="contact mt-5c" id="contact">
    <div class="container">
      <h2 class="contact__heading text-uppercase">Contact</h2>
      <p class="contact__intro">
        If you like my work, and have a business idea, don’t hesitate to contact
        me! let’s take your business to the next level.
      </p>
      <address class="mb-5">
        Business Email :
        <a href="mailto:achraf.fawzi.A@gmail.com" class="contact__email"
          >Achraf.fawzi.a@gmail.com</a
        >
      </address>

      <form
        id="gform"
        method="POST"
        data-email="from_email@example.com"
        action="https://script.google.com/macros/s/AKfycbxcLSNwKBCcvyeU0Ls2s2Y_e2mo38wDjbqlfFTB-JCjQlLbdwEKaBi6p8NtG3S3F-ze/exec"
      >
        <div class="row">
          <div class="col-lg-5">
            <div class="form-group">
              <label for=""></label>
              <input
                type="text"
                class="form-control"
                id="name"
                name="name"
                placeholder="Fullname"
                required
              />
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-5">
            <div class="form-group">
              <label for=""></label>
              <input
                type="email"
                class="form-control"
                id="email"
                name="email"
                placeholder="Email address"
                required
              />
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-5">
            <div class="form-group">
              <label for=""></label>
              <textarea
                class="form-control"
                rows="7"
                placeholder="Message"
                name="message"
                id="message"
                required
              ></textarea>
            </div>
          </div>
        </div>
        <input type="submit" class="button-send my-4" value="Send" />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
};
</script>

<style lang="scss" scoped>
@import "../scss/home/variables.scss";
.contact {
  margin-top: 100px;

  .contact__heading {
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

  .contact__intro {
    margin: 40px 0 10px;
  }

  .contact__email {
    color: $pinkish-color;
  }

  input:-webkit-autofill,
  input:-webkit-autofill:hover,
  input:-webkit-autofill:focus,
  input:-webkit-autofill:active {
    transition: background-color 5000s ease-in-out 0s;
    -webkit-text-fill-color: $white-color !important;
  }

  input,
  textarea {
    background: rgba(37, 40, 55, 0.7);
    border: none;
    border-bottom: 1px solid $white-color;
    padding-left: 0;
    outline: none;
    color: $white-color;
  }

  .form-control:focus {
    box-shadow: none;
    border-bottom: 1px solid $white-color;
  }

  .button-send {
    color: $white-color;
    border: 1px solid $white-color;
    padding: 5px 10px;
    transition: background-color 0.2s linear, color 0.2s linear;

    &:hover {
      color: #333;
      background-color: $white-color;
    }
  }
}
</style>
