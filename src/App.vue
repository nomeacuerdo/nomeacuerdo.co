<template>
  <div id="application">
    <div class="block nav">
      <Navigation />
    </div>
    <div class="block content" v-if="cheemz">
      <router-view/>
    </div>
    <div class="block footer">
      <Footer />
    </div>
    <easteregg @easter="egg" :duration="duration">
      <img alt="bonk" src="./assets/cheemz.png">
    </easteregg>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import easteregg from '@/components/easteregg.vue';
import Navigation from '@/components/Navigation.vue';
import Footer from '@/components/Footer.vue';

export default defineComponent({
  name: 'nomeacuerdo.co',
  components: {
    Navigation,
    Footer,
    easteregg,
  },
  data() {
    return {
      cheemz: true,
      duration: 500,
    };
  },
  methods: {
    egg() {
      this.cheemz = false;
      setTimeout(() => { this.cheemz = true; }, this.duration);
    }
  }
});
</script>

<style lang="scss">
:root {
  --background: #003049;
  --text: #eae2b7;
  --highlight: #d62828;
  --link: #f77f00;
  --vue-green: #3eaf7c;
  --vue-inactive: #fcbf49;
}

body {
  background-color: var(--background);
  margin: 0;
}

@keyframes reveal {
  to {
    filter: brightness(100%);
    opacity: 1;
  }
}

a {
  color: var(--link);
  font-weight: bold;
  padding: 2px 5px;
  position: relative;
  text-decoration: none;
  transition: .4s;
  z-index: 1;

  &:after {
    background-color: var(--link);
    mix-blend-mode: overlay;
    bottom: 0;
    content: "";
    height: 0;
    left: 0;
    position: absolute;
    transition: .4s;
    width: 100%;
    z-index: 0;
  }

  &:hover {
    span {
      color: var(--background);
    }

    &:after {
      height: 30px;
    }
  }

  &.router-link-exact-active {
    text-decoration: underline;

    &:after {
      background-color: transparent;
    }
  }
}

#application {
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  color: var(--text);
  font-family: 'M PLUS Rounded 1c', sans-serif;
  position: relative;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  min-height: 95vh;
  z-index: 0;
  opacity: 0;
  filter: brightness(0%);

  animation: reveal 0.4s cubic-bezier(0.0, 0.0, 0.58, 1.0) forwards {
    delay: 1s;
  }

  &:after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0.03;
    filter: invert(100%);

    background: {
      attachment: fixed;
      image: url('./assets/logo.svg');
      clip: padding-box;
      origin: padding-box;
      position: 95% 95%;
      repeat: no-repeat;
      size: 20vw 20vw;
    }
  }

  .block {
    z-index: 1;
    flex-grow: 1;
    max-width: 1080px;

    @media screen and (max-width: 640px) {
      max-width: 550px;
    }
  }

  .nav,
  .footer {
    flex-grow: 0;
    text-align: center;
  }
}
</style>
