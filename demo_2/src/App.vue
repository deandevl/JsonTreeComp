<template>
  <div class='demo_container'>
    <json-tree-comp
        title="Food Information from USDA"
        :json_obj="json_obj"
        :css_variables="css_variables">
      <div></div>
    </json-tree-comp>
  </div>
</template>

<script>
  import JsonTreeComp from 'jsontreecomp';

  export default {
    name: 'App',
    data: function() {
      return {
        json_obj: null,
        css_variables: {
          jsontree_comp_color: 'white',
          jsontree_comp_title_color: 'white',
          jsontree_comp_width: '460px'
        }
      };
    },
    components: {
      JsonTreeComp
    },
    methods: {
      load_JSON: function(){
        const xobj = new XMLHttpRequest();
        xobj.overrideMimeType('application/json');
        xobj.open('GET','data/food.json',true);
        xobj.onreadystatechange = ()=>{
          if(xobj.readyState === 4 && xobj.status === 200){
            this.json_obj = JSON.parse(xobj.responseText);
          }
        };
        xobj.send(null);
      }
    },
    mounted: function(){
      this.load_JSON();
    }
  }
</script>

<style>
  .demo_container {
    background-color: black;
    padding: 20px;
    width: 1100px;
    height: 700px;
    overflow: auto;
  }
</style>