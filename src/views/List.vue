<template>
  <div class="list">
    <header>
      <div class="title"><span>Search an</span> <strong>anime</strong></div>
      <br /><br />
      <form class="search" @submit.prevent="fetchData">
        <input
          type="search"
          class="search-box"
          placeholder="text to be here..."
          v-model="search"
          required
        />
      </form>
      <br /><br />
    </header>
    <main>
      <div class="card">
        <br />
        <Card v-for="(anime, index) in list" :key="index" :anime="anime" />
        <br />
      </div>
    </main>
  </div>

  <main></main>
</template>

<script>
import { ref } from "@vue/reactivity";
import Card from "../components/Card.vue";

export default {
  name: "List",
  components: { Card },
  setup() {
    const search = ref("");
    const list = ref([]);
    const fetchData = async () => {
      list.value = await fetch(`https://api.jikan.moe/v3/search/anime?q=${search.value}`)
        .then((res) => res.json())
        .then((data) => data.results);

      console.log(list.value);
    };

    return { Card, search, list, fetchData };
  },
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  background-color: hsl(215, 54%, 11%);
}

.title {
  text-align: center;
  font-family: "Fira Sans", sans-serif;
  text-transform: uppercase;
  font-size: 60px;
}

.title span {
  color: #fff;
  text-shadow: 0 0 20px rgb(97, 179, 255);
}

.title strong {
  color: rgb(250, 66, 66);
  text-shadow: 0 0 20px crimson;
}

.search {
  text-align: center;
}

.search-box {
  font-size: 20px;
  width: 90%;
  text-align: center;
  padding: 5px;
  border: none;
  border-radius: 20px;
  transition: 0.2s ease-in-out;
  background: rgba(161, 161, 161, 0.295);
}

.search-box:hover {
  outline: none;
  box-shadow: 0 0 10px rgb(97, 179, 255);
  background: rgba(161, 161, 161, 0.15);
  color: #fff;
}

.search-box:focus,
.search-box:valid {
  outline: none;
  box-shadow: 0 0 20px rgb(97, 179, 255);
  background: rgba(161, 161, 161, 0.082);
  color: #fff;
}

.search-box::placeholder {
  transition: 0.2s ease-in-out;
  font-family: "Fira Sans", sans-serif;
  color: rgba(128, 128, 128, 0.425);
}

main {
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 200%;
  margin: 0 auto;
  padding-left: 30px;
  padding-right: 30px;
}

main .card {
  display: flex;
  flex-wrap: wrap;
  margin: 5 0px;
}
</style>
