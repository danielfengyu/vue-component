<template>
		<div :id="test.id">
			<template v-for="item in test.lays" >
				<my-layout v-if="hasChildLayout(item)" :test="item"></my-layout>
				<div v-else :id="item.id"><my-app @msgfromchild="printChildMsg"></my-app></div>
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
			hasChildLayout:function(layout){
				return layout.lays.length > 0;
			},
			printChildMsg:function(data){
				alert(data);
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