<template>
		<div>
			<div v-for="item in (test.vLay||test.hLay)" v-if="isObj(item)">
				<my-table :test="item"></my-table>
			</div>
			<div v-else></div>
		</div>
</template>

<script type="text/javascript">
	export default {
		name: "MyTable",
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

		}
	}
</script>
	
<style type="text/css">
	
</style>