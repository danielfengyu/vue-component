<template>
    <ul>
        <div @click='toggle' @mouseover="print(treeData.data.menuName)">
            <i v-if='isFolder' class="fa " :class="[open?'fa-folder-open':'fa-folder']"></i>
            <i v-if='!isFolder' class="fa fa-file-text"></i> {{treeData.data.menuName}}
        </div>
        <ul v-show="open" v-if='isFolder'>
            <my-tree v-for='cel in treeData.childTreeNode' :tree-data='cel' :key="cel.id"></my-tree>
        </ul>
    </ul>
</template>
<script>
    export default {
        name:"MyTree",
        props:["treeData"],
        data() {
             return {
                open: false,
                //isFolder: true
            }
        },
        computed:{
            isFolder: function() {
                return this.treeData.childTreeNode && this.treeData.childTreeNode.length
            }
        },
        methods: {
            toggle: function() {
                if(this.isFolder) {
                    this.open = !this.open
                }
            },
            print:function(name){
                alert(name);
            }
        },

    }
</script>

<style>

</style>