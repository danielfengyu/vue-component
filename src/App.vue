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
        <div style="height:1000px;width:320px;">
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

  var data = [{
        "id": "1",
        "data": {
            "menuName": "项目管理",
            "menuCode": "",
        },
        "childTreeNode": [{
            "id": "1_1",
            "data": {
                "menuName": "项目",
                "menuCode": "BusProject",
            },
            "childTreeNode": []
        }, {
            "id": "1_2",
            "data": {
                "menuName": "我的任务",
                "menuCode": "BusProject",
            },
            "childTreeNode": []
        }, {
            "id": "1_3",
            "data": {
                "menuName": "人员周报",
                "menuCode": "BusProject",
            },
            "childTreeNode": []
        }]
    }, {
        "id": "2",
        "data": {
            "menuName": "数据统计",
            "menuCode": "BusClock",
        },
        "childTreeNode": []
    }, {
        "id": "3",
        "data": {
            "menuName": "人事管理",
            "menuCode": "",
        },
        "childTreeNode": []
    }, {
        "id": "4",
        "data": {
            "menuName": "基础管理",
            "menuCode": "",
        },
        "childTreeNode": []
    }];
  export default {
    name: 'app',
    data() {
      return {
        msg: 'Welcome to Daniel\'s blog',
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
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
#header {
  position: fixed;
  width:100%;
  height: 61px;
  top: 0;
  left: 0;
  box-shadow: 0 0 1px rgba(0,0,0,0.25);
  transition: background-color 0.3s ease-in-out;
  background-color: #fff;
  padding: 6px 60px;
  z-index: 2;
  display: block;
}

#body {
  position: relative;
  top: 61px;
  z-index: 1;
  padding: 0 60px 30px;
  overflow-x: hidden;
}
#siderbar {
  position: fixed;
  z-index: 10;
  top: 73px;
  left: 0;
  bottom: 0;
  overflow-x: hidden;
  overflow-y: auto;
  background-color:#fff;
}

div {
  display: block;
}

.content {
  position: relative;
  padding: 2.2em 0;
  max-width: 600px;
  margin: 0 auto;
  padding-left: 30px;
  background-color: rgba(162, 156, 156, 0.04);
}
#log {
  display: inline-block;
  font-size: 1.5em;
  line-height: 40px;
  color: #2c3e50;
  font-family: 'Dosis', 'Source Sans Pro', 'Helvetica Neue', Arial, sans-serif;
  font-weight: 500;
}

#logo img {
    vertical-align: middle;
    margin-right: 6px;
    width: 40px;
    height: 40px;
}

img {
    border: none;
}

#nav {
  list-style-type: none;
  margin: 0;
  padding: 0;
  position: fixed;
  right: 30px;
  top: 10px;
  height: 40px;
  line-height: 40px;
}

ul, menu, dir {
    display: block;
    list-style-type: disc;
    -webkit-margin-before: 1em;
    -webkit-margin-after: 1em;
    -webkit-margin-start: 0px;
    -webkit-margin-end: 0px;
    -webkit-padding-start: 10px;
}
</style>
