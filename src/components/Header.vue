<template>
  <header>
    <div class="content">
      <div class="input__wrapper">
        <input
          type="search"
          placeholder="Search for a photo..."
          required
          v-model="search_query"
          @keyup.enter="HandleSearch"
        />
        <i class="fas fa-search"></i>
      </div>
    </div>
  </header>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Header',

  props: {
    inputValue: String,
    default: '',
  },
  data() {
    return {
      photos: [],
      search_query: '',
      uri: 'https://api.unsplash.com/photos/?client_id=',
      apiKey: process.env.VUE_APP_MAP_KEY,
    };
  },
  created() {
    return axios
      .get(`${this.uri}${this.apiKey}&query=${this.search_query.value}`)
      .then((response) => {
        this.photos = response.data;
        console.log(response.data);
      })
      .catch((error) => {
        console.log(error);
      });
  },
  method: {
    HandleSearch(value) {
      if (photos.value.length > 1) {
        return axios
          .get(`${this.uri}${this.apiKey}&query=${this.search_query.value}`)
          .then((response) => {
            this.photos = response.data;
            console.log(response.data);
          })
          .catch((error) => {
            console.log(error);
          });
      } else {
        console.log(data);
      }
      search_query.value = '';
    },
  },
};
</script>

<style>
header {
  background-color: #dde2e9;
  height: 15rem;
}
.input__wrapper {
  position: relative;
  max-width: 100%;
}
.input__wrapper input {
  width: 100%;
  padding: 1.2rem 4rem;
  font-size: 1rem;
  border-radius: 0.3rem;
  outline: none;
  border: none;
  margin-top: 4rem;
}
.input__wrapper i {
  color: gray;
  position: absolute;
  top: 5.2rem;
  left: 2rem;
  height: 1.5rem;
}
</style>
