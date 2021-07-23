<template>
  <div class="card">
    <a :href="anime.url" target="_blank">
      <img :src="anime.image_url" alt="img not available" />
      <h3>{{ anime.title }}</h3>
    </a>
  </div>
</template>

<script>
import { onMounted } from "@vue/runtime-core";
// import { ref } from '@vue';
export default {
  name: "Card",
  props: ["anime"],
  setup(props) {
    onMounted(() => {
      console.log(props.anime);
    });
  },
};
</script>

<style>
.card {
  display: flex;
  flex: 1 1 100%;
  align-items: center;
  justify-content: center;
  width: 100%;
  max-width: 100%;
  padding: 0 8px;
  margin-bottom: 16px;
}

.card img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 20px;
  box-shadow: 0 0 10px rgb(100, 246, 74);
  transition: 0.4s;
}

.card a {
  text-decoration: none;
}

.card h3 {
  text-align: center;
  padding: 15px;
  transition: 0.4s ease-in-out;
  color: #fff;
}

.card img:hover {
  box-shadow: 0 0 20px rgb(97, 179, 255);
  transform: scale(1.05);
}

.card h3:hover {
  color: rgb(97, 179, 255);
}
</style>
