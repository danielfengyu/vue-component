<template>
  <div v-if="ok">
  	 <h1>{{title}}</h1>
     <p>{{content}}</p>
  </div>
</template>

<script>
	export default {
		name:"MyApp",
		data(){
			return {
				ok:false,
				title: "My first app!",
				content: "Paragraph 1"
			}
		}
	}
</script>

<style>
	h1{
		color: red;
	}
</style>