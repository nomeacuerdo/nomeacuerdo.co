<template>
  &copy; nomeacuerdo.co {{year}}. Image by <a :href="links.jhonny" target="_blank">Alejandro Henao.</a>
  <br />
  Made with <a :href="links.vue" target="_blank" class="vuejs"><i class="fab fa-vuejs"></i></a>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Footer',
  data() {
    return {
      links: {
        jhonny: 'http://instagram.com/henaoylopez',
        vue: 'https://vuejs.org/',
      }
    };
  },
  computed: {
    year() {
      return new Date().getUTCFullYear();
    }
  }
});
</script>

<style scoped lang="scss">
  .vuejs {
    color: var(--vue-blue);
    
    &:hover {
      background-color: transparent;
      color: var(--vue-green);
    }
  }
</style>