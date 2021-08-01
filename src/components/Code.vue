<template>
  <div>
    <div class="row">
      <h1>Linkes</h1>

    </div>

    <div class="cards">
      <Card
          v-for="card in cards"
          :key="card.title"
          :title="card.title"
          :description="card.description"
          :emoji="card.emoji"
          :link="card.link"
      ></Card>
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Code",
  components: {Card},
  data() {
    return {
      cards: [
        {
          title: "github",
          emoji: "🐱",
          description: "My github page",
          link: "https://github.com/natsupon",
        },
        {
          title: "Qiita",
          emoji: "✎",
          description: "勉強メモ",
          link: "https://qiita.com/naccchan",
        },
        {
          title: "Note",
          emoji: "📓",
          description: "About me",
          link: "https://note.com/natsumin_723/",
        },
      ],
    };
    // eslint-disable-next-line no-unreachable
    isExpanded = false;
  },
  methods: {
    expandDiv() {
      const div = document.querySelector(".cards");
      const chevron = document.getElementById("chevron");

      if (!this.isExpanded) {
        div.classList.add("expandedCards");
        chevron.style.transform = "rotate(180deg)";
        this.isExpanded = true;
      } else {
        div.classList.remove("expandedCards");
        chevron.style.transform = "rotate(0deg)";
        this.isExpanded = false;
      }
      console.log(div.classList);
    },
  },
};
</script>

<style scoped>
.cards {
  grid-gap: 1rem;
  margin: 0 auto;
  display: grid;
  height: 320px;
  overflow: hidden;
}

@media screen and (max-width: 580px) {
  .cards {
    height: 315px;
  }
}

.expandedCards {
  height: 100%;
}

@media (min-width: 600px) {
  .cards {
    grid-template-columns: repeat(2, 1fr);
  }
}

.rotate {
  transform: rotate(180deg);
}

.no-rotate {
  transform: rotate(0deg);
}

@media screen and (min-width: 370px) {
  .cards {
    height: 302px;
  }
}

@media screen and (min-width: 900px) and (max-width: 1040px) {
  .cards {
    height: 370px;
  }
}

h1 {
  font-weight: 500;
  color: white;
  font-size: 1.8rem;
  border-bottom: 10px solid #dad0c7;
  line-height: 0.4;
  width: 40px;
  transition: all ease 0.3s;
}

.row {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

svg {
  color: white;
}

.row button {
  border: none;
  padding: 10px;
  border-radius: 8px;
  background-color: #a9ac9c;
}

.row button:hover {
  background-color: #a9ac9c;
  transition: background-color ease 0.2s;
  cursor: pointer;
}

.row button:focus {
  outline: none;
}
</style>
