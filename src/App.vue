<template>
  <div id="app">
    <cursor-fx color="#ffa89f"color-hover="#ffa89f"></cursor-fx>
    <div class="home">
      <div>
        <button class="scroll-top" v-on:click="scrollToTop">
          <i id="scroll-top" class="fas fa-chevron-up fa-lg"></i>
        </button>
      </div>
      <Navbar></Navbar>
      <HorizontalDivider></HorizontalDivider>
      <Hero></Hero>
      <Code></Code>
      </div>
      <HorizontalDivider></HorizontalDivider>
      <Footer></Footer>
    </div>
  </div>

</template>

<script>
import Navbar from "./components/Navbar.vue";
import HorizontalDivider from "./components/HorizontalDivider.vue";
import Hero from "./components/Hero.vue";
import Code from "./components/Code.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Navbar,
    HorizontalDivider,
    Hero,
    Code,
    Footer
  },
  data() {
    return {
      projects: null,
    };
  },
  mounted() {
    // This will break one day
    // TODO: Use own API key
    const url =
        "https://natsumi-portfolio.herokuapp.com/";
    $.ajax({
      url: url,
      type: "get",
      data: {projects: {}},
      dataType: "jsonp",
    })
        .done((response) => {
          let data = [];
          let res = response.projects;
          console.log(response);
          for (let i = 0; i < res.length; i++) {
            data.push({
              src: res[i].covers.original,
              link: res[i].url,
              name: res[i].name,
            });
          }
          this.projects = data;
        })
        .fail((error) => {
          console.error(error);
        });
  },
  methods: {
    scrollToTop() {
      window.scrollTo({top: 0, left: 0, behavior: "smooth"});
    },
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  padding: 0;
  margin: 0;
}

body {
  background-color: #a7adb1;
  font-family: "canada-type-gibson";
  overflow-x:hidden;
}

::-webkit-scrollbar {
  width: 8px;
}

/* Track */
::-webkit-scrollbar-track {
  background: #a7adb1;
  border-radius: 0.5rem;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #cfc5c5;
  border-radius: 0.5rem;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #cfc5c5;
}

.scroll-top {
  position: fixed;
  bottom: 15%;
  left: 85%;
  background-color: #cfc5c5;
  border: none;
  margin-left: 2rem;
  padding: 10px;
  display: flex;
  border-radius: 8px;
  justify-content: center;
  align-items: center;
  transition: all ease 0.2s;
  z-index: 2;
}

.scroll-top:hover {
  transform: scale(1.2);
  transition: 0.5s;
  color: white;
}

.home {
  max-width: 870px;
  margin: 2rem auto;
}

.art {
  font-weight: 500;
  color: white;
  font-size: 1.8rem;
  border-bottom: 10px solid #cfc5c5;
  line-height: 0.4;
  width: 40px;
  transition: all ease 0.3s;
}

.art:hover {
  font-size: 1.8rem;
  font-weight: 500;
  color: white;
  border-bottom: 10px solid #cfc5c5;
  line-height: 0.4;
  width: 90px;
  transition: 0.5s;
}


@media screen and (max-width: 1500px) {
  .home {
    margin: 2rem 20rem;
  }
}

@media screen and (max-width: 1380px) {
  .home {
    margin: 2rem 15rem;
  }
}

@media screen and (max-width: 936px) {
  .home {
    margin: 2rem;
  }

  .scroll-top {
    visibility: hidden;
  }
}

@media screen and (max-width: 320px) {
  .home {
    margin: 2rem 1rem;
  }
}
</style>
