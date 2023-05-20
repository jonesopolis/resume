<template>
  <div class="d-flex justify-content-center">
    <vue3-word-cloud style="height: 480px; width: 640px;" 
    :words="[
            
            ['C#', 20],
            ['.NET', 20],
            ['Azure', 20],
            ['Cloud Services', 20],
            ['DevOps', 20],
            ['MVC', 20],

            ['Pipelines', 15],
            ['SOLID / DRY', 15],
            ['Pipelines', 15],
            ['SAAS', 15],

            ['CSS', 10],
            ['SCSS', 10],
            ['LESS', 10],
            
            ['Integrations', 5],
            ['Discovery', 5]          
          
          ]
            " 

    :color="([, weight]) => weight > 15 ? '#fff' : weight > 10 ? 'RoyalBlue' : weight > 5 ? 'lightblue' :'Indigo'" 
    font-family="Anton" 
    :rotation="(word) => Chance(word[0]).pickone([0, 3 / 4])" />
  </div>
</template>

<script>
import Vue3WordCloud from 'vue3-word-cloud';
import Chance from 'chance';

export default {
  components: {
    Vue3WordCloud: Vue3WordCloud,
  },
  data() {
    return {
      Chance: Chance
    };
  }
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Anton');
</style>
