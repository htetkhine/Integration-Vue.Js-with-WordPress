# Integration-Vue.Js-with-WordPress
This repo is very helpful to integrate Vue.Js with WordPress

# Vue 3 
​
An approachable, performant, and versatile framework for building web user interfaces.
Learn More [Vue.Js Website](https://vuejs.org/)
​
## Function add in wordpress
​
**Firstly open wordpress function.php**
​
```bash
define('TEMPLATE_URL', get_stylesheet_directory_uri());
define('ASSET_URL', TEMPLATE_URL . '/assets/');
function enqueue_vue_3() {
   wp_enqueue_script('Vue', 'https://unpkg.com/vue@3/dist/vue.global.js', array(), null, true);
   wp_enqueue_script('calculator-script', ASSET_URL . 'js/vue.js', array(), null, true); 
}
add_action('wp_enqueue_scripts', 'enqueue_vue_3');
```
​
**Create .js file and vue register**
​
```bash
const { createApp, ref } = Vue;
const app = Vue.createApp({});

app.component("something", {    
    template: "#something",
    setup() {
      //write here business logic
    }
})
app.mount('#app');
```
​
**Paste your component template**
​
```bash
<div id="app">
   <div class="container">
     <div class="row">
       <div class="col-12">
          <something></something> 
       </div>
     </div>
   </div>  
 </div>
<?php  get_template_part('component/something');?>
```
​
**Create Your Template id must be registered name in .js file**
​
```bash
<template id="something">
</template>
```

