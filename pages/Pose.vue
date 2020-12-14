<template>
<div class="grid-container">
<div class="header">
<header>
<div class="logo">
<img src="../assets/images/yoga-chakra.jpg" id ="yoga-chakra" alt="man sitting in ayogic posture">
</div>
<h1>Yoga</h1>
</header>
</div>
<div class="nav-bar">
<nav>
<ul class="nav-links">
<li v-for="item in items" v-bind:key="item"><a v-bind:href="item.path">{{item.name}}</a></li>
</ul>
</nav>
</div>

<div>
<main class="main">
<div class="wrapper">
    <h1 class="heading">Countries of Europe</h1>
    <section class="container" v-if="yogaposes">
        <asana
          v-for="pose of yogaposes"
          :key="pose.id"
          :pose="pose"
        />
    </section>
  </div>



</main>
</div>







<div class="footer">
<p class="footer-text">© Copyright 2020 Swati. All rights reserved.</p>
</div>

</div>
  
</template>

<script>
import Asana from '../components/Asana.vue'
import axios from 'axios'

export default {
    name: 'Pose',
  components: {
    Asana,
  },
  data() {
    return {
      loading: true,
      yogaposes: null,
      errored: false
    }
  },
  mounted () {
  axios
    .get('https://raw.githubusercontent.com/rebeccaestes/yoga_api/master/yoga_api.json')
    .then(response => (this.yogaposes = response.data))
    .catch(error => {
      console.log(error)
      this.errored = true
    })
    .finally(() => this.loading = false)
  }
  
}
</script>

<style>
.container {
  min-height: 100vh;
  max-width: 1200px;
  margin: auto;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  text-align: center;
  flex-wrap: wrap;
}

.heading {
  text-align: center;
  font-size: 2rem;
  color: #555;
  margin: 2rem auto;
}

img {
  max-width: 150px;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

