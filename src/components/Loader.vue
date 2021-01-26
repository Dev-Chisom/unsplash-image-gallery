<template>
  <div class="gallery">
    <div class="card-1">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-2">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-3">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-4">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-5">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-6">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-7">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-8">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-9">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-10">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-11">
      <div class="name"></div>
      <div class="place"></div>
    </div>
    <div class="card-12">
      <div class="name"></div>
      <div class="place"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Loader',
};
</script>

<style scoped>
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
.card-1,
.card-2,
.card-3,
.card-4,
.card-5,
.card-6,
.card-7,
.card-8,
.card-9,
.card-10,
.card-11,
.card-12 {
  position: relative;
  width: 250px;
  height: 400px;
  display: block;
  background: #eee;
  border-radius: 5px;
  animation: lds-spinner 1s linear infinite;
  /* margin: 1rem; */
  /* box-shadow: 0px 3px 30px 8px rgba(0, 0, 0, 0.1); */
}
.card-1,
.card-3,
.card-4,
.card-6,
.card-7,
.card-9,
.card-10,
.card-12 {
  width: 250px;
  height: 300px;
}
.card-4,
.card-6 {
  margin-top: -4rem;
  /* margin-bottom: 0; */
}

.card-7,
.card-9 {
  margin-top: -9rem;
}
.card-10,
.card-12 {
  margin-top: -14rem;
}
.card-5,
.card-8,
.card-11 {
  margin-top: 1rem;
}
.card-11 {
  height: 200px;
}
.name {
  position: absolute;
  background-color: #bbb;
  bottom: 40px;
  left: 10px;
  width: 150px;
  height: 11px;
  margin: 10px;
  animation: load-anim 1.2s infinite linear;
}
.place {
  position: absolute;
  background-color: #bbb;
  bottom: 20px;
  left: 10px;
  width: 100px;
  height: 11px;
  margin: 10px;
  animation: load-anim 1.2s infinite linear;
}

@keyframes lds-spinner {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0.3;
  }
}
@keyframes load-anim {
  0% {
    background-position: -200px;
  }
  100% {
    background-position: 300px;
  }
}
@media (max-width: 768px) {
  .gallery {
    grid-template-columns: repeat(2, 1fr);
    left: 4rem;
  }
  .card-1,
  .card-2,
  .card-3,
  .card-4,
  .card-5,
  .card-6,
  .card-7,
  .card-8,
  .card-9,
  .card-10,
  .card-11,
  .card-12 {
    margin: 0;
    width: 250px;
    height: 400px;
  }
}
@media (min-width: 320px) and (max-width: 660px) {
  .gallery {
    grid-template-columns: auto;
    place-items: center;
    left: 3rem;
  }
  .card-1,
  .card-2,
  .card-3,
  .card-4,
  .card-5,
  .card-6,
  .card-7,
  .card-8,
  .card-9,
  .card-10,
  .card-11,
  .card-12 {
    margin: 0;
    width: 250px;
    height: 400px;
  }
}
@media (max-width: 860px) and (min-width: 660px) {
  .gallery {
    grid-template-columns: repeat(2, 1fr);
    left: 7rem;
  }
  .card-1,
  .card-2,
  .card-3,
  .card-4,
  .card-5,
  .card-6,
  .card-7,
  .card-8,
  .card-9,
  .card-10,
  .card-11,
  .card-12 {
    margin: 0;
    width: 250px;
    height: 400px;
  }
}
@media (max-width: 1024px) and (min-width: 860px) {
  .gallery {
    left: 4rem;
  }
}
@media (max-width: 2560px) and (min-width: 2000px) {
  .gallery {
    left: 22rem;
  }
  .card-1,
  .card-2,
  .card-3,
  .card-4,
  .card-5,
  .card-6,
  .card-7,
  .card-8,
  .card-9,
  .card-10,
  .card-11,
  .card-12 {
    margin: 1rem;
    width: 350px;
    height: 600px;
  }
}
</style>
