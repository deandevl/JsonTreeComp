<template>
  <div class='demo_container'>
    <json-tree-comp
        title="Employee Family Information"
        :json_obj="json_obj"
        :css_variables="css_variables">
      <div id="topdiv"></div>
    </json-tree-comp>

    <p>Information gathered by Icon.inc</p>
  </div>
</template>

<script>
  import JsonTreeComp from 'jsontreecomp';

  export default {
    name: 'App',
    data() {
      return {
        json_obj: null,
        css_variables: {
          jsontree_comp_color: 'white',
          jsontree_comp_title_color: 'white'
        }
      };
    },
    components: {
      JsonTreeComp
    },
    mounted: function(){
      this.json_obj = {
        'name':'Billy Bob',
        'favorite number': 3,
        'veteran': true,
        'address info':{
          'street':'123 Edward Ave',
          'city':'Richmond',
          'state':'Virginia',
          'coordinates':[{'latitude':32.4567},{'longitude':67.8965}],
          'neighbors':{'right':'Roger','left':'Jane','across':'Sydney'},
        },
        'children':[{'name':'Bob','age':10},{'name':'Tommy','age':13},{'name':'Nancy','age':15}]
      }
    }
  }
</script>

<style>
  .demo_container {
    background-color: black;
    color: white;
    padding: 30px;
    width: 1100px;
    height: 700px;
  }
</style>