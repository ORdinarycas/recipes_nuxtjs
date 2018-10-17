<template>
  <section class="recipes">
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :id="recipe.id"
      :previewText="recipe.previewText" />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
  components: {
    Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: '1',
              title: 'Deliioue Pizza',
              previewText:'Awesome Pizza!',
              thumbnail: '//cheersbar.com.au/wp-content/uploads/2016/01/CheersBar-Food-76.jpg'
            },
            {
              id: '2',
              title: '奔麒麟',
              previewText:'奔麒麟sasd Pizza!',
              thumbnail: '//food.fnr.sndimg.com/content/dam/images/food/fullset/2018/4/30/0/FNK_Ice-Cream-in-a-Bag_s4x3.jpg.rend.hgtvcom.826.620.suffix/1525105614384.jpeg'
            }
          ]
        })
      },0)
    })
  }
};
</script>

<style scoped>
  .recipes {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
  }
</style>
