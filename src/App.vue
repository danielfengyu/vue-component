  <template>
  <div id="app">
    <div id="header">
      <a id="logo" href="/">
        <img src="./assets/logo1.png">
        <span>Vue.js</span>
      </a>
      <ul id="nav">
         {{msg}}
     </ul>
    </div>
    <div id="body">
      <div id="siderbar">
        <div style="margin-left:36px;max-width:284px;">
         <!--my-list></my-list>-->
         <my-tree  v-for='data in treeData' :tree-data='data' :key="data.id"></my-tree>
        </div>
      </div>
      <div id="content" class="content">
        <my-layout :test="layoutObj"></my-layout>
      </div>
    </div>
  </div>
</template>

<script>
  import MyApp from "./components/MyApp.vue";
  import MyList from "./components/MyList.vue";
  import MyLayout from "./components/MyLayout.vue";
  import MyTree from "./components/MyTree.vue";

  import data from "./assets/datas/treedata.json"; 

  export default {
    name: 'app',
    data() {
      return {
        msg: 'Welcome to Daniel\'s blog',
        layoutObj: {
          id:"layer1",
          size:"100%",
          layout:"hLay",
					lays: [
						{
              id:"layer2-1",
              size:"400",
              layout:"vLay",
              lays: [
                  {
                      id:"layer3-1",
                      size:"400",
                      layout:"vLay",
                      lays: [

                      ]
                  },
                  {
                      id:"layer3-2",
                      size:"400",
                      layout:"vLay",
                      lays: [

                      ]
                  }
              ]
            },
						{
							id:"layer2-2",
              size:"auto",
              layout:"hLay",
              lays: [

              ]
						}
					],
				},
        treeData:data
      }
    },
    components: {
      MyApp,
      MyList,
      MyLayout,
      MyTree,
    }
  }
</script>

<style>
/*"./assets/css/app.css"可以放到这里*/
</style>
