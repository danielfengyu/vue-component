<template>
		<div>
			<template v-for="item in (test.vLay||test.hLay)" >
				<my-layout v-if="isObj(item)" :test="item"></my-layout>
				<div v-else><my-app></my-app></div>
			</template>
		</div>
</template>

<script type="text/javascript">
   import MyApp from "./MyApp.vue";
	export default {
		name: "MyLayout",
		props: ['test'],
		data(){
			return {}
		},
		methods: {
			hasLayObj: function(obj){
				if(obj.hasOwnProperty("hLay")||obj.hasOwnProperty("vLay")){
					return true;
				}
				return false;
			},
			isObj: function(item){
				return typeof item === "object";
			},
			layoutArr:function(ob){
				if(obj.hasOwnProperty("hLay")){
					return obj.hLay;
				}
				if(obj.hasOwnProperty("vLay")){
					return obj.vLay;
				}
				return [];
			}
		},
		computed: {

		},
		components: {
			MyApp
		}
	}
</script>
	
<style type="text/css">
	
</style>