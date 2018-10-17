<template>
  <nuxt-link :to="'/recipes/' + id">
    <section class="recipes">
      <article class="recipe">
        <div class="thumbnail" :style="{backgroundImage: 'url(' + thumbnail + ')'}"></div>
        <h1>{{ title }}</h1>
        <p>{{ previewText }}</p>
      </article>
    </section>
  </nuxt-link>
</template>

<script>
  export default {
    props: ['thumbnail', 'title', 'previewText', "id"]
  };
</script>

<style scoped>
  a {
    text-decoration: none;
    color: black;
  }
  .recipe {
    box-sizing: border-box;
    margin: 10px;
    width: 250px;
    padding: 8px;
    border: 1px solid rgb(43, 19, 19);
    box-shadow: 0 2px 2px #aaa;
  }
  .thumbnail {
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 200px;
  }
</style>
