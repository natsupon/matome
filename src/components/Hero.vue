<template>
  <div class="hero">
    <div class="image-holder">
      <img src="../assets/me.png" alt="Image of Natsumi Arai"/>
    </div>
    <div class="text">
      <div class="top-text">
        <h1>
          Hi, I'm Natsumi Arai! 🐍
        </h1>
        <h2>
          元SE、前職日本コンピュータシステム株式会社
        </h2>
      </div>
      <div class="bottom-text">
        <p class="b-margin">
          出身大学は <a
            target="_blank"
            rel="noopener noreferrer"
            class="pink"
            href="http://www.ns.kogakuin.ac.jp/~wwc1001/"
        >工学院大学工学部第一部電気システム工学科</a
        >です。</p>
       </div>
      <br>
    </div>
  </div>
</template>

<script>
import {VueTyper} from 'vue-typer'

export default {
  name: "Hero",
  components: {
    VueTyper
  },
};
</script>

<style scoped>
.color {
  /* border-bottom: 4px solid #1da7ea; */
  color: #ffa89f;
}

ul {
  margin: 0;
  list-style-type: none;
  display: flex;
  flex-direction: row;
}

li {
  margin-left: 2rem;
  padding: 10px;
  display: flex;
  border-radius: 8px;
  justify-content: center;
  align-items: center;
  background-color: #ffa89f;
  transition: all ease 0.2s;
}

li:hover {
  background-color: #ffa89f;
  transform: translateY(-5px);
  transition: all ease 0.2s;
}

::v-deep .typed {
  color: #ffa89f !important;
}

::v-deep .custom.caret {
  background-color: #ffa89f !important;
}

.fa-twitter {
  color: #fff;
}

.pink {
  color: #254a55;
  text-decoration: none;
  font-weight: bolder;
  margin: 5px;
  transition: siz;
}

.green-text {
  color: lawngreen;
}

.pink:hover {
  color: #697470;
  text-decoration: none;
  font-weight: bolder;
  margin: 5px;
  transition: siz;
}

.center {
  text-align: center;
}

img {
  height: 400px;
  border-radius: 8px;
}

.b-margin {
  margin-bottom: 1rem;
}

.image-holder {
  height: 125px;
}

.hero {
  display: flex;
  margin-bottom: 2rem;
}

.text {
  height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: white;
  margin-left: 2rem;
}

a {
  text-decoration: none;
}

h1,
p {
  margin: 0;
}

h1 {
  font-weight: 500;
  font-size: 1.8rem;
}

h2 {
  font-weight: 480;
  font-size: 1.4rem;
}

p {
  font-weight: 300;
  font-size: 1rem;
  line-height: 1.3;
  /* text-align: justify; */
}

.fa-linkedin {
  color: white;
}

@media screen and (max-width: 1258px) {
  .hero {
    flex-direction: column;
    margin-bottom: 0rem;
  }

  img {
    height: 150px;
    width: auto;
    clip-path: circle(60px at center);
    position: relative;
    top: -20px;
    margin: 0;
  }

  .text {
    margin-left: 0;
    height: auto;
  }

  h1 {
    margin-bottom: 1rem;
    margin-top: 1rem;
  }

  li {
    margin-right: 0.5rem;
    margin-left: 0.5rem;
  }

  .contact {
    margin-top: 16px;
  }
}
</style>
