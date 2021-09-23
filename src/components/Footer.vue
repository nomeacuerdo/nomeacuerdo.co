<template>
  <footer>
    &copy; nomeacuerdo.co {{year}}.
    <br />
    Image by <a :href="links.jhonny" target="_blank"><span>Alejandro Henao.</span></a> Made with <a :href="links.vue" target="_blank" class="vuejs"><i class="fab fa-vuejs"></i></a>
  </footer>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Footer',
  data() {
    return {
      links: {
        jhonny: 'http://instagram.com/colorcontradiction',
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
  footer {
    padding-bottom: 25px;
  }
  .vuejs {
    color: var(--vue-inactive);

    &:after {
      background-color: transparent;
    }
    
    &:hover {
      color: var(--vue-green);
    }
  }
</style>