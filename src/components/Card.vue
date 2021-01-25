<template>
  <div class="container">
    <div v-if="loading">
      <Loader />
    </div>
  </div>
</template>

<script>
import Loader from './Loader';
import axios from 'axios';
export default {
  name: 'Card',
  components: {
    Loader,
  },
  data() {
    return {
      loading: false,
      photos: [],
      search_query: '',
      uri: 'https://api.unsplash.com/photos/?client_id=',
      apiKey: process.env.VUE_APP_MAP_KEY,
    };
  },
  created() {
    return axios
      .get(`${this.uri}${this.apiKey}`)
      .then((response) => {
        this.photos = response.data;
        // console.log(response.data);
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style></style>
