<template>
  <div class="app">
    <HeaderComponent title="&quot;Fala Português&quot; Gerador de Tendências" />
    <TendencyComponent :tendency="tendency" />
    <div class="button-container">
      <button @click="getTendencia">Nova tendência</button>
    </div>
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import TendencyComponent from "./components/TendencyComponent.vue";
import data from "./data/words.json"

export default {
  name: "App",
  components: {
    HeaderComponent,
    TendencyComponent
  },
  data() {
    return {
      tendency: ""
    };
  },
  created() {
    this.getTendencia();
  },
  methods: {
    async getTendencia() {
      const randomAdjective = data.adjectives[Math.floor(Math.random() * data.adjectives.length)];
      const randomNoun = data.nouns[Math.floor(Math.random() * data.nouns.length)];

      const randomTendencia = `${randomAdjective} ${randomNoun}`;

      this.tendency = randomTendencia;
    }
  }
};
</script>

<style lang="scss">
:root {
  --primary: #42b883;
  --secondary: #35495e;
  --dark: #1a1a1a;
  --lite: #e1e1e1;
  --gray: #2f2f2f;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.button-container {
  display: flex;
  justify-content: center;
  padding: 0 20px;
  margin: 40px auto;
  button {
    color: var(--primary);
    border: none;
    background-color: var(--secondary);
    padding: 10px 20px;
    font-size: 22px;
    border-radius: 20px;
    cursor: pointer;
    transition: 0.4s;

    &:hover {
      background-color: var(--gray);
    }
  }
}
</style>

