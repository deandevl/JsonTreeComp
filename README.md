## json-tree-comp

**json-tree-comp** is a Vue.js (>= 2.5) web component that displays a JSON formatted object as a hierarchical tree.  

**json-tree-comp** depends on the [vue.js](https://vuejs.org/ "Vue.js") framework.  The dependency can be installed via [npm install](https://docs.npmjs.com/cli/install.html "npm install") with the included `package.json` file. Three [webpack](https://webpack.js.org/concepts/) npm scripts are included for building  development, production, or hot recompile/execute of the demo.   `build-dev` and `build-prod` scripts produce  a `dist` folder containing the `index.html`.  The size of the `main.js` bundle using `build-prod` is 11 KiB along with calling a CDN for incorporating the Vue framework.

## Props

A prop in Vue.js is a custom attribute for passing information from a parent component hosting **json-tree-comp** instance(s) to a **json-tree-comp** as a child component. 

**json-tree-comp** has the following props for a parent to bind to child:

  `json_obj` -- an object or array of objects to be displayed

  `title` -- a title to be placed above the tree (string, default: null)

  `indent` --  the number of spaces to indent sub nodes

  `css_variables` -- defines the css variables for **json-tree-comp** (object, default: null)

## Styling

The `css_variables` prop is a javascript object that contains any combination of css variable names as keys and associated values.  The following list are the css variable names along with their default values for a quick styling of **json-tree-comp**:

```
    {
      jsontree_comp_height: 600px,
      jsontree_comp_width: 400px,
      jsontree_comp_font_family: 'Verdana,serif',
      jsontree_comp_font_size: '1rem',
      jsontree_comp_color: 'black',
      jsontree_comp_background: 'transparent',

      jsontree_comp_down_icon: '\21D3',
      jsontree_comp_title_color: 'black'
    }
```

## Events

There are no events.

## Demonstration

Two demonstrations of **json-tree-comp** are provided in the folders named `demo_1` and `demo_2` and can be viewed by hosting the `index.html` files in the `dist` folders.  The demo's views were templated in the `App.vue` files.

As a suggestion, install [http-server](https://www.npmjs.com/package/http-server "http-server") globally via [npm](https://www.npmjs.com/ "npm") then enter the command `http-server`in the **json-tree-comp** `dist` directory.  From a browser enter the url: `localhost:8080/` to view the demo.

Here is some example code for using **json-tree-comp** taken from its `App.vue` file:

```
      <json-tree-comp
        title="Employee Family Information"
        :json_obj="json_obj"
        :css_variables="css_variables">
        <div></div>
      </json-tree-comp>
```

And here are the data references:

```
   data() {
    return {
      json_obj: null,
      css_variables: {
        jsontree_comp_color: 'white',
        jsontree_comp_title_color: 'white'
      }
    }
  }
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
```

