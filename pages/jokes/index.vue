<template>
  <div>
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke";

export default {
  components: {
    Joke
  },
  data() {
    return {
      jokes: []
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const resp = await axios.get("https://icanhazdadjoke.com/search", config);
      this.jokes = resp.data.results;
    } catch (error) {
      console.log(error);
    }
  },
  head() {
    return {
      title: "Jokes",
      meta: [
        {
          hid: "welcome",
          name: "welcome",
          content: "Best place for corny dad jokes"
        }
      ]
    };
  }
};
</script>

<style></style>
