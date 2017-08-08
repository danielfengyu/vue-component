<template>
		<div v-if="hasHLayObj(test)">
			<div v-for="item in test.hLay" v-if="isObj(item)">
				<my-table :test="item"></my-table>
			</div>
			<div v-else></div>
		</div>
		<div v-else>
			<div v-for="item in test.vLay" v-if="isObj(item)">
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
			return {
				layoutObj: {
					hLay: [
						"400",
						{
							vLay: [
								"400",
								"auto"
							],
						}
					],
				}
			}
		},
		methods: {
			hasHLayObj: function(obj){
				if(obj.hasOwnProperty("hLay")){
					return true;
				}
				return false;
			},
			hasVLayObj: function(obj){
				if(obj.hasOwnProperty("vLay")){
					return true;
				}
				return false;
			},
			isObj: function(item){
				return typeof item === "object";
			}
		},
		computed: {

		}
	}
</script>
	
<style type="text/css">
	
</style>