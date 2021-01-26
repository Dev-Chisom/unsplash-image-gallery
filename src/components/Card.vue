<template>
  <div class="container">
    <div v-if="loading">
      <Loader />
    </div>
    <div class="gallery">
      <div class="card" v-for="photo in photos" :key="photo">
        <img :src="photo.urls.regular" :alt="photo.alt_description" />
        <!-- <p>{{ photo.alt_description }}</p> -->
        <p class="name">
          <span style="padding-right:10px;">{{ photo.user.first_name }} </span
          ><span>{{ photo.user.last_name }}</span>
        </p>
        <p class="place">{{ photo.user.location }}</p>
      </div>
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
      loading: true,
      photos: [],
      search_query: '',
      uri: 'https://api.unsplash.com/photos/?client_id=',
      apiKey: process.env.VUE_APP_MAP_KEY,
    };
  },
  created() {
    setTimeout(() => (this.loading = false), 2000);
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
};
</script>

<style scoped>
img {
  width: 100%;
  height: 60vh;
  object-fit: cover;
}
span {
  display: inline-block;
}
.gallery {
  position: absolute;
  top: 10rem;
  left: 15rem;
  width: 70%;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: auto;
  gap: 20px;
}
.name {
  position: absolute;

  bottom: 40px;
  left: 10px;
  width: 150px;
  height: 11px;
  margin: 10px;
}
.place {
  position: absolute;

  bottom: 20px;
  left: 10px;
  width: 100px;
  height: 11px;
  margin: 10px;
}
.gallery > div {
  position: relative;
  width: 250px;
  height: 400px;
  display: block;
  border-radius: 5px;
}
.gallery > div:nth-child(1),
.gallery > div:nth-child(3),
.gallery > div:nth-child(4),
.gallery > div:nth-child(6),
.gallery > div:nth-child(7),
.gallery > div:nth-child(9) {
  width: 250px !important;
  height: 300px !important;
}
.gallery > div:nth-child(10),
.gallery > img:nth-child(10) {
  width: 250px;
  height: 200px;
}
</style>
