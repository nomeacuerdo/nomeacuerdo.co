<template>
  <div class="home">
    <img alt="nomeacuerdo" src="../assets/nomeacuerdo.png">
    <span class="hello">Hello there!</span>
    <h1>My name is <strong>Nicolás Arteaga Nieto</strong></h1>
    <h2>I'm a <strong>Frontend Developer</strong> based on <strong>Bogotá, Colombia</strong>.</h2>
    <Curriculum />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Curriculum from '@/components/Curriculum.vue'; // @ is an alias to /src

export default defineComponent({
  name: 'Home',
  components: {
    Curriculum,
  },
});
</script>
<style lang="scss">
  .hello {
    display: block;
    font-size: 2em;
    font-weight: 700;
  }

  h1 {
    font-size: 3em;

    strong {
      @media screen and (max-width: 640px) {
        display: block;
      }
    }
  }

  .home {
    text-align: center;

    strong {
      color: var(--highlight);
    }
    img {
      max-width: 250px;
    }
  }
</style>
