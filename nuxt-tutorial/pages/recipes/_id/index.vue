<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{recipe.descriptionText}}</p>
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
                id: "1",
                title: "Barbecue Pizza",
                previewText: "Good Pizza",
                descriptionText: "Made with Barbecue",
                thumbnail: "https://gardeninthekitchen.com/wp-content/uploads/2016/05/bbq-ck-pizza6-1.jpg"
              },
              {
                id: "2",
                title: "Philly Cheese Steak Sammich",
                previewText: "Delicious Sammich",
                descriptionText: "Made with Steak",
                thumbnail: "http://www.recipe4living.com/assets/itemimages/400/400/3/default_47a0ab21d606eda585dab5efe1c9b47c_dreamstime_s_35101343.jpg"
              }
            ].find(el => el.id === context.params.id)
          })
        }, 1000)
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

  .recipe-image {
    width: 100%;
  }
</style>
