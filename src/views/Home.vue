<template>
  <div class="home">
    <section>
      <video src="../assets/bg.mp4" autoplay muted loop></video>
      
      <h1>Ani Me <router-link class="main" to="/list">Create <strong>YOUR ANIME DAIRY</strong></router-link></h1>
    </section>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {

}
}
</script>
<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Fira Sans', sans-serif;
}

section{
  position: absolute;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

section h1 .main{
  text-decoration: none;
  padding: 0 15px;
  font-size: 50px;
  color: #2196F3;
  letter-spacing: 4px;
  overflow: hidden;
  transition: 0.2s;
  border: 2px solid #2196F3;
  border-radius: 15px ;
  box-shadow:0 0 10px #2196F3 ;
}

section h1 .main:hover{
  color: black;
  background: #2196F3;
  box-shadow: 0 0 10px #2196F3,0 0 30px #2196F3,0 0 50px #2196F3;
}

section video{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

section h1{
  position: absolute;
  top: 0%;
  left: 0%;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  text-transform: uppercase;
  font-size: 10vw;
  color: #fff;
  background: rgba(12, 19, 31, 0.99);
  mix-blend-mode: multiply;
  font-weight: 200;
}

</style>