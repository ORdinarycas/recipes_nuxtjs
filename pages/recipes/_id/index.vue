<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{ recipe.previewText }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: '1',
              title: 'Deliioue Pizza',
              previewText:'Awesome Pizza dsfsdfsfdsaaaaaa!',
              thumbnail: '//cheersbar.com.au/wp-content/uploads/2016/01/CheersBar-Food-76.jpg'
            },
            {
              id: '2',
              title: '奔麒麟',
              previewText:'奔麒麟sasd Pizza!',
              thumbnail: '//food.fnr.sndimg.com/content/dam/images/food/fullset/2018/4/30/0/FNK_Ice-Cream-in-a-Bag_s4x3.jpg.rend.hgtvcom.826.620.suffix/1525105614384.jpeg'
            }
          ].find(el => el.id === context.params.id)
        })
      },0)
    })
  }
}
</script>


<style scoped>
  .single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
  }
</style>
