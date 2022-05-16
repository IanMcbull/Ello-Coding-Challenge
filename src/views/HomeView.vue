<template>
  <v-container>
    <div class="home">
    <div v-if="$apollo.loading" style="color: green;"><vue-loaders-ball-scale-ripple-multiple color="currentColor" scale="1"></vue-loaders-ball-scale-ripple-multiple></div>
    <div class="pages">
    <p>{{book.pages[1].content}}</p>
    <p>{{book.pages[2].content}}</p>
    </div>
    <!-- <p v-else v-for="content in book.pages" :key="book.pages.indexOf(content)" class="content">{{content.content}}</p> -->
  </div>
  </v-container>
</template>

<script>
import gql from 'graphql-tag';
import 'vue-loaders/dist/vue-loaders.css';
import VueLoaders from 'vue-loaders';
import Vue from 'vue'
Vue.use(VueLoaders);
export default {
  name: 'HomeView',
  apollo:{
    book: gql`query{
      book{
        pages{
          content
          tokens{
            value
            position
          }
        }
      }
    }`
  },
  data:()=>({
    book:''
  })
}
</script>
<style scoped>
 .home{
   padding: 10px;
 }
 .pages{
   display: flex;
   font-size:3rem;
   gap:100px;
 }
 .home > .content{
   margin-top: 5px;
 }
 .pages > p{
   width: 50%;
   text-align: justify;
 }
</style>