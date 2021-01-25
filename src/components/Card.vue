<template>
  <div class="container">
    <div v-if="loading">
      <Loader />
    </div>
    <div v-else class="card" v-for="photo in filteredPhotos" :key="photo">
      <img
        :src="photo.urls ? photo.urls.raw : ''"
        :alt="photo.alt_description"
      />
      <p>{{ photo.location }}</p>
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
      search: '',
      uri: 'https://api.unsplash.com/photos/?client_id=',
      apiKey: process.env.VUE_APP_MAP_KEY,
    };
  },
  created() {
    return axios
      .get(`${this.uri}${this.apiKey}`)
      .then((response) => {
        this.photos = response.data;
        console.log(response.data);
      })
      .catch((error) => {
        console.log(error);
      });
  },
  computed: {
    filteredPhotos() {
      return this.photos.filter((country) => {
        return country.name
          .toLowerCase()
          .includes(this.search.toString().toLowerCase());
      });
    },
  },
};
</script>

<style></style>
