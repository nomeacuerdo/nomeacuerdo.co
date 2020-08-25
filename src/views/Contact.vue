<template>
  <div class="contact">
    <h1>Find me at:</h1>
    <ul class="links">
      <li v-for="item in links" :key="item.title">
        <a :href="item.url" :alt="item.title" :style="`--item-color: ${item.color};`" target="_blank" rel="noopener noreferrer">
          <i :class="item.icon"></i>
        </a>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Contact',
  data() {
    return {
      links: [
        {
          icon: 'far fa-envelope',
          title: 'Mail',
          url: 'mailto:nomeacuerdo@gmail.com?subject=Contact from nomeacuerdo.co&body=Hi! I come in peace.',
          color: '#F14336',
        }, {
          icon: 'fab fa-linkedin',
          title: 'Linkedin',
          url: 'https://www.linkedin.com/in/nomeacuerdo/',
          color: '#0077b5',
        }, {
          icon: 'fab fa-github',
          title: 'Github',
          url: 'https://github.com/nomeacuerdo',
          color: '#24292e',
        }, {
          icon: 'fab fa-instagram',
          title: 'Instagram',
          url: 'https://instagram.com/nomeacuerdo',
          color: '#C13584',
        }, 
      ]
    };
  },
});
</script>

<style scoped lang="scss">
  .contact {
    min-width: 480px;
  }
  .links {
    display: flex;
    list-style: none;
    padding: 0;

    li {
      flex-grow: 1;
      text-align: center;
    }

    a {
      color: var(--color);
      font-size: 5em;

      &:hover {
        background-color: transparent;
        color: var(--item-color);
      }
    }
  }
</style>
