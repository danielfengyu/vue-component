<template>
	<ul>
		<li v-for="item in items" v-bind:title='item.title' v-on:click="sayHello(item.title)">{{item.title}}</li>
	</ul>
</template>

<script>
	export default {
		name:"MyList",
		data(){
			return {
				items: [
					{
						title: "hello"
					},{
						title: "nihao"
					}
				]
			}
		},
		methods:{
			sayHello (msg) {
				alert(msg);
			}
		},
		filters:{
		
		},
		watch:{

		}
	}
</script>
