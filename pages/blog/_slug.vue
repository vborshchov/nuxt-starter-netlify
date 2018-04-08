<template>
  <article>
    <h1>{{ title }}</h1>
    <vue-markdown>{{body}}</vue-markdown>
  </article>
</template>

<script>
import VueMarkdown from 'vue-markdown'

export default {
  components: {
    VueMarkdown
  },
  async asyncData({ params }) {
    // const postPromise = process.BROWSER_BUILD
    //   ? import('~/content/blog/posts/' + params.slug + '.json')
    //   : Promise.resolve(
    //       require('~/content/blog/posts/' + params.slug + '.json')
    //     );

    let post = await import('~/content/blog/posts/' + params.slug + '.json');
    return post;
  }
};
</script>
