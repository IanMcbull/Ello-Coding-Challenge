<template>
  <v-app>
    <p>{{book.author}}</p>
  </v-app>
</template>

<script>
import gql from 'graphql-tag'
export default {
  name: 'App',
  apollo: {
      book: gql`query{
        book{
          author
        }
      }`
    },
  data: () => ({
    //
  }),
};
</script>
