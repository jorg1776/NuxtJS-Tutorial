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
                id: "1",
                title: "Barbecue Pizza",
                previewText: "Good Pizza",
                thumbnail: "https://gardeninthekitchen.com/wp-content/uploads/2016/05/bbq-ck-pizza6-1.jpg"
              },
              {
                id: "2",
                title: "Philly Cheese Steak Sammich",
                previewText: "Delicious Sammich",
                thumbnail: "http://www.recipe4living.com/assets/itemimages/400/400/3/default_47a0ab21d606eda585dab5efe1c9b47c_dreamstime_s_35101343.jpg"
              }
            ]
          })
        }, 1000)
      })
    }
  }
</script>


<style scoped>
  .recipes {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
  }
</style>
