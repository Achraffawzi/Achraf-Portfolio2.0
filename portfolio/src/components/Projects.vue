<template>
  <div class="projects" id="projects">
    <div class="container">
      <h2 class="projects__heading text-uppercase">Projects</h2>
    <div v-if="projects.length > 0" class="mt-5">
      <div class="carousel-div" v-if="dataLoaded">
        <carousel
          v-if="dataLoaded"
          :items="2"
          :autoplay="false"
          :nav="false"
          :responsive="{
            0: { items: 1, nav: false },
            600: { items: 1, nav: false },
          }"
        >
          <a
            v-for="project in projects"
            :key="project.title"
            :href="project.link"
            target="_blank"
            class="text-white text-decoration-none row"
          >
            <div class="col-lg-6 image-col">
              <img
                :src="project.picture"
                class="img-fluid project-image"
                data-aos="zoom-in-right"
              />
            </div>
            <div class="col-lg-6">
              <div>
                <h3 class="mb-4 projects__title text-uppercase">
                  {{ project.title }}
                </h3>
                <p class="mb-5 projects__desc">{{ project.description }}</p>
                <p class="projects__technologies text-uppercase">
                  <span class="d-block mb-2">technologies used :</span>
                  <i
                    v-for="technology in project.technologies"
                    :key="technology"
                    :class="technology"
                  ></i>
                </p>
              </div>
            </div>
          </a>
        </carousel>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
import carousel from "vue-owl-carousel";
import projectsData from "../projects.json";
export default {
  name: "Projects",
  data() {
    return {
      projects: [],
      dataLoaded: false,
    };
  },
  components: { carousel },
  mounted() {
    this.projects = projectsData["projects"];
    if (this.projects != null) {
      this.dataLoaded = true;
    }
  },
  created() {
    //   this.projects = projectsData;
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/home/variables.scss";
.projects {
  margin-top: 150px;

  .projects__heading {
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

  i[class^="devicon"] {
    font-size: 20px;
    margin: 0 10px;

    &:first-of-type {
      margin-left: 0;
    }
  }
}

.image-col {
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
