<template>
  <div class="cv">
    <h2>I <em>mainly</em> work with these technologies:</h2>
    <ul class="links">
      <li v-for="item in techLinks" :key="item.title">
        <a :href="item.url" target="_blank">
          <i :class="item.icon"></i>
          <span>{{item.title}}</span>
        </a>
      </li>
    </ul>
    <h2>And these are the tools that I use more frequently:</h2>
    <ul class="links">
      <li v-for="item in toolsLinks" :key="item.title">
        <a :href="item.url" target="_blank">
          <i :class="item.icon"></i>
          <span>{{item.title}}</span>
        </a>
      </li>
    </ul>

    <p class="hobbies">
      On the technical side, I have a Computer Science degree and I've worked for over 10 years
       in development, 7 of them focused on Frontend development.
      <br /><br />
      Through this journey
       I've picked skills to work on agile environments, lead technical teams
       and even teach a thing or two. The two principal things that I consider that a project
       must have are clean code and a clean git repository.
      <br /><br />
      On my spare time I play videogames (currently my heart is with Nintendo Switch), play
       Magic: the Gathering and binge watch a couple of series at a time. I intend to go as soon
       as possible on a previously planned (but sadly cancelled) trip to Japan. Also, probably
       polish my cooking skills.
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import '../assets/brandie.css';

export default defineComponent({
  name: 'Curriculum',
  data() {
    return {
      techLinks: [
        {
          url: 'https://reactjs.org',
          title: 'ReactJS',
          icon: 'fab fa-react',
        }, {
          url: 'https://v3.vuejs.org',
          title: 'VueJS',
          icon: 'fab fa-vuejs',
        }, {
          url: 'https://nodejs.org',
          title: 'NodeJS',
          icon: 'fab fa-node-js',
        }, {
          url: 'https://www.gatsbyjs.com/',
          title: 'Gatsby',
          icon: 'icon-gatsby',
        }, {
          url: 'https://shopify.dev',
          title: 'Shopify',
          icon: 'fab fa-shopify',
        }, {
          url: 'https://graphql.org/',
          title: 'GraphQL',
          icon: 'icon-graphql',
        },
      ],
      toolsLinks: [
        {
          url: 'https://code.visualstudio.com',
          title: 'Code',
          icon: 'icon-vscode',
        }, {
          url: 'https://git-scm.com',
          title: 'Git',
          icon: 'fab fa-git-alt',
        }, {
          url: 'https://firebase.google.com/',
          title: 'Firebase',
          icon: 'icon-firebase',
        }, {
          url: 'https://aws.amazon.com/',
          title: 'AWS',
          icon: 'fab fa-aws',
        }, {
          url: 'https://www.sketch.com/',
          title: 'Sketch',
          icon: 'fab fa-sketch',
        }, {
          url: 'https://www.adobe.com/products/photoshop.html',
          title: 'Photoshop',
          icon: 'icon-photoshop',
        }, {
          url: 'https://docs.docker.com/compose/',
          title: 'Docker Compose',
          icon: 'fab fa-docker',
        },
      ],
    };
  },
});
</script>

<style scoped lang="scss">
  .cv {
    padding: 15px 0 25px;
  }

  .links {
    display: flex;
    list-style: none;
    padding: 0 25px;
    min-height: 80px;
    flex-wrap: wrap;

    li {
      flex-grow: 1;
      text-align: center;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      margin: 30px 15px 0;
      min-width: 75px;

      a {
        display: flex;
        flex-direction: column;
        height: 100%;
      }

      i {
        flex-grow: 2;
        font-size: 2em;
        padding-bottom: 10px;
      }
      span {
        flex-grow: 0;
      }
    }
  }

  .hobbies {
    padding: 50px 0;
    margin: auto;
    max-width: 80vw;
  }
</style>
