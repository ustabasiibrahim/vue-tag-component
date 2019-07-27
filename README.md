# vue-tag-component

This is Tags Input Component created by VueJS

## Getting Started

These instructions will get you a copy of the component up and running on your local machine.

### Installing

You can install vue-component-tag component by npm

```
npm install vue-component-tag
```

After download, vue-component-tag will be ready to use in your VueJS Applications

### Usage

* Just import Components from node_modules folder in main.js

```
import Tags from "vue-component-tag"
```

* Register vs-tags component with any name you want

```
Vue.component("vtag", Tags);
```

After this step, vue-tag-component can be used by all registered component in your project with vtag tag name 

* You can use with <vtag></vtag>

```
<vtag></vtag>
```

#### Styling

vue-component-tag has 6 color options

* primary
* success
* danger
* info
* warning

To use these colors, just add 'color' attribute into vtag component

```
<vtag color="primary"></vtag>
```

```
<vtag color="secondary"></vtag>
```

```
<vtag color="success"></vtag>
```

```
<vtag color="danger"></vtag>
```

```
<vtag color="info"></vtag>
```

```
<vtag color="warning"></vtag>
```

#### Data Binding

Also you can bind vue-tag-component component by v-model VueJS directive

```
<vtag v-model="tags"></vtag>
```

This data property will give us all tags with comma seperator.

```
vuejs,inputtag,ibrahimustabasi,tag-component
```

## Versioning

We use [GitHub](https://github.com/ustabasiibrahim/vue-tag-component) for versioning. For the versions available, see the [tags on this repository](https://github.com/ustabasiibrahim/vue-tag-component/tags). 

## Authors

* **İbrahim Ustabaşı** - [İbrahim Ustabaşı](https://github.com/ustabasiibrahim)

## License

This project is licensed under the MIT License

