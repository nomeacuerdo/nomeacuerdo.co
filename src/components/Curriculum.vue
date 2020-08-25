<template>
  <div class="cv">
    <h2>I <em>mainly</em> work with these technologies:</h2>
    <ul class="links">
      <li v-for="item in techLinks" :key="item.title"><a :href="item.url" target="_blank">{{item.title}}</a></li>
    </ul>
    <h2>And these are the tools that I use more frequently:</h2>
    <ul class="links">
      <li v-for="item in toolsLinks" :key="item.title"><a :href="item.url" target="_blank">{{item.title}}</a></li>
    </ul>

    <p class="hobbies">
      On the technical side, I have a Computer Science degree and I've worked for over 10 years in development, 7 of them focused on Frontend development. Through this journey I've picked skills to work on agile environments, lead technical teams and even teach a thing or two.
      <br /><br />
      One of the things that I love about my job is writing clean, polished code using a perfectly streamlined git workflow. The challenge of reaching that point in a project is where the real work is. Another important thing for me is bringing a personal and human touch to each project.
      <br /><br />
      On my spare time I play videogames (currently my heart is with Nintendo Switch), play Magic: the Gathering and binge watch a couple of series at a time.
      <br /><br />
      After we get over the pandemic, I intend to go on a previously planned (but sadly cancelled) trip to Japan. Also, probably polish my cooking skills.
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Curriculum',
  data() {
    return {
      techLinks: [
        {
          url: 'https://reactjs.org',
          title: 'ReactJS',
        }, {
          url: 'https://v3.vuejs.org',
          title: 'VueJS',
        }, {
          url: 'https://nodejs.org',
          title: 'NodeJS',
        }, {
          url: 'https://www.gatsbyjs.com/',
          title: 'Gatsby',
        }, {
          url: 'https://shopify.dev',
          title: 'Shopify',
        }, {
          url: 'https://graphql.org/',
          title: 'GraphQL',
        }, 
      ],
      toolsLinks: [
        {
          url: "https://code.visualstudio.com",
          title: 'Code',
        }, {
          url: "https://git-scm.com",
          title: 'Git',
        }, {
          url: "https://firebase.google.com/",
          title: 'Firebase',
        }, {
          url: "https://aws.amazon.com/",
          title: 'AWS',
        }, {
          url: "https://docs.docker.com/compose/",
          title: 'Docker Compose',
        }, {
          url: "https://www.sketch.com/",
          title: 'Sketch',
        }, {
          url: "https://www.adobe.com/products/photoshop.html",
          title: 'Photoshop',
        }
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
    padding: 0;

    li {
      flex-grow: 1;
      text-align: center;
    }
  }

  .hobbies {
    padding: 50px 0;
    margin: auto;
    min-width: 450px;
    max-width: 80vw;
  }
</style>