<template>
  <div class="about page  animate__animated animate__fadeIn">
    <h2>Recent Project</h2>
    <div class="container">
      <div class="row" v-for="(project, index) in projects" :key="index">
        <div class="col-md-5">
          <b-link target="blank" :href="project.image_cover">
          <img
            :src="project.image_cover"
            :alt="project.title"
            class="project-cover"
          />
          </b-link>
        </div>
        <div class="col-md-5">
          <h2 class="mt-3" style="text-align: left;">
            {{ project.title }}
            <hr class="dope" />
          </h2>
          <b-card class="mt-3 mb-3 text-left text-dark">
            <p>{{ project.description }}</p>
            <b-link target="blank" :href="project.link"
              >Check it out! <LinkIcon style="color: #000;"
            /></b-link>
            <hr v-if="project.github_url" />
            <b-link v-if="project.github_url" target="blank" :href="project.github_url"
              >View source code <GithubIcon style="color: #000;"
            /></b-link>

            <hr />
            <div class="mt-3 mb-3 text-dark">
              {{ project.tag }}
            </div>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import LinkIcon from "vue-ionicons/dist/md-link.vue";
import GithubIcon from "vue-ionicons/dist/logo-github.vue";

export default {
  components: {
    GithubIcon,
    LinkIcon
  },
  data() {
    return {
      projects: [
        {
          title: "App - Embarque rápido",
          tag: "#CapacitorJS - #Js - #Android - #GooglePlay - #Vuejs",
          description:
            "App para realizar o embarque e desembarque dos passageiros e controle de bagagens da empresa Eucatur Transportes.",
          image_cover: "https://uploaddeimagens.com.br/images/004/530/664/full/app-embarque.png?1688474502",
          github_url: "",
          link: "https://play.google.com/store/apps/details?id=br.com.eucatur.app_embarque"
        },
        {
          title: "All Projects",
          tag: "#Golang, #ReactJs, #HooksReact",
          description:
            "Plataforma de gerenciamento de projetos",
          image_cover: "https://uploaddeimagens.com.br/images/004/530/751/full/poject-all.png?1688476729",
          github_url: "",
          link: "https://app.allprojects.com.br/dashboard"
        },
        {
          title: "E-commerce Eucatur",
          tag: "#Golang, #Js, #Vuejs, #QuasaJs, #SCSS",
          description:
            "Site de vendas de passagem da empresa Eucatur",
          image_cover: "https://uploaddeimagens.com.br/images/004/530/774/full/ecommerce-eucatur.png?1688477275",
          github_url: "",
          link: "https://www.eucatur.com.br/"
        }
      ],
    };
  },
  methods: {
    isEven(n) {
      if (n % 2 == 0) {
        return true;
      } else {
        return false;
      }
    }
  },
  head: {
    title: "Recent Projects 💻 - Asaolu Elijah",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "View all the recents open-sourced projects built with ♥ by Asaolu Elijah, open-sourced means this project source code are publicly available for everyone to use or modify."
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Recent Projects 💻 - Asaolu Elijah"
      },
      {
        property: "og:description",
        content:
          "View all the recents open-sourced projects built with ♥ by Asaolu Elijah, open-sourced means this project source code are publicly available for everyone to use or modify."
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/man-computer.png")
      }
    ]
  }
};
</script>
<style scoped>
.row {
  margin-top: 70px;
}
.project-cover {
  width: 300px;
  height: 240px;
  border-radius: 3px;
}
hr.dope {
  border: 0;
  width: 90px;
  border-top: 2px solid #dc3545;
  text-align: left;
  margin: initial;
  margin-top: 7px;
  margin-left: 5px;
}
</style>
