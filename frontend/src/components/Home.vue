
<template>
<div class="container">
	<header>
		<div  class="row pt-1 align-items-center">
			<div id="div-logo" class="col-3 col-md-5">
				<img src="../assets/appdvice-logo.png">
			</div>
			<div id="div-titulo" class="col align-middle">
				<h1 class="">Appdvice</h1>
			</div>
		</div>
	</header>
	<div class="row mt-4">
		<div class="col">
			<h2 class="h1">Make your decision as if you were...</h2>
		</div>
	</div>
</div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      randomNumber: 0
    }
  },
  methods: {
    getRandomInt (min, max) {
      min = Math.ceil(min)
      max = Math.floor(max)
      return Math.floor(Math.random() * (max - min + 1)) + min
    },
    getRandom () {
      // this.randomNumber = this.getRandomInt(1, 100)
      this.randomNumber = this.getRandomFromBackend()
    },
    getRandomFromBackend () {
      const path = `http://localhost:5000/api/random`
      axios.get(path)
      .then(response => {
        this.randomNumber = response.data.randomNumber
      })
      .catch(error => {
        console.log(error)
      })
    }
  },
  created () {
    this.getRandom()
  }
}
</script>
