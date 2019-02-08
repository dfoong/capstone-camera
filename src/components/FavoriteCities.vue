<template>
    <ul class="favorite-cities">
        <li><h2>Favorite Cities</h2></li>
        <li v-if="favoriteCities.length < 1">No favorites cities to display.</li>
        <li v-for="(city,index) in favoriteCities" :key="index">
          <router-link v-bind:to="{ name: 'CurrentWeather', params: { cityId: city.id } }">{{ city.name }}</router-link> <button v-on:click="removeCity(city)" class="remove">x</button>
        </li>
    </ul>
</template>

<script>
export default {
  name: 'FavoriteCities',
  data () {
    return {}
  },
  props: {
    favoriteCities: Array
  },
  methods: {
    removeCity: function (city) {
      // TODO: Add logic to remove a city from the `favoriteCities` array.
      // Hint: Use `indexOf(city)` on the `this.favoriteCities` array and then use the `splice()` method

      // TODO: Save the new favoriteCities array to the cache.
    }
  }
}
</script>

<style scoped>
.favorite-cities {
  list-style-type: none;
  padding: 10px;
  background: #ccc;
  width: 25%;
  float: right;
}
.remove {
  font-size: 0.8rem;
  color: white;
  background: #AA0000;
  padding: 2px;
  cursor: pointer;
}
</style>