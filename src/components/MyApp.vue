<template>
  <div v-if="ok">
  	 <h1>{{title}}</h1>
     <p>{{content}}</p>
	 <button @click="sengMsgToParent">点击我</button>
  </div>
</template>

<script>
	export default {
		name:"MyApp",
		data(){
			return {
				ok:true,
				title: "My first app!",
				content: "Paragraph 1"
			}
		},
		methods:{
			sengMsgToParent:function(){
				this.$emit("msgfromchild","message from child");
			}
		}
	}
</script>

<style>
	h1{
		color: blue;
	}
</style>