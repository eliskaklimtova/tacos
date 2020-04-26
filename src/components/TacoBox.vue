<template>
	<div class="container">
		<h1>{{ title }}</h1>
		<h2>Do you want tacos?</h2>
		<div class="tacos-wrap" v-if="wantTacos === true">
			<h3>Here's some tacos for you!</h3>
			<div class="tacos" v-for="taco in tacos" :key="taco.id">🌮</div>
		</div>
		<div class="no-tacos-wrap" v-if="wantTacos === false">
			<h3>Ok, no tacos for you! <b>¯\_(ツ)_/¯</b></h3> 
		</div>
		<button 
			class="nope"
			@click="noTacos"
		>
			Nope
		</button>
		<button 
			class="yas"
			@click="getTacos"
		>
			{{ greenButtonText }}
		</button>
	</div>
</template>

<script>
export default {
	name: 'TacoBox',
	props: ['title'],
	data() {
		return {
			wantTacos: '',
			greenButtonText: 'Yaaass',
			tacos: []
		}
	},
	methods: {
		getTacos() {
			this.wantTacos = true
			this.greenButtonText = 'Give me more tacos'

			this.tacos++
		},
		noTacos() {
			this.wantTacos = false
			this.greenButtonText = 'Yaaass'

			this.tacos = []
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
	margin: 120px auto 0 auto;
}

h1 {
	font-size: 64px;
}

h2 {
	font-size: 40px;
	margin-bottom: 70px;
}

h3 {
	font-weight: 400;
	font-size: 22px;
}

button {
	border: none;
	border-radius: 5px;
	color: #fff;
	cursor: pointer;
	font-size: 20px;
	font-weight: 600;
	margin: 60px 20px;
	padding: 20px;
	transition: ease all .3s;
	width: 230px;
}

button:focus {
	outline: none;
}

.yas {
	background-color: #21C481;
}

.yas:hover {
	background-color: rgb(28, 160, 105);
}

.nope {
	background-color: #FF5A5A;
}

.nope:hover {
	background-color: rgb(194, 75, 75);
}

.tacos {
	font-size: 56px;
	margin: 30px 10px 0 0;
	display: inline-flex;
}
</style>
