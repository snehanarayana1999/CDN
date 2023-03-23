<template>
    <body>
        <ul class="sidebar">
        
        <li v-for="item in data" :key="item.id">
          
          <h1 v-on:click="item.show = !item.show" >
             {{item.name}}
            <span class="material-symbols-outlined">arrow_drop_down</span>
          </h1>
        <ul class="side-menu">
    
          <ul v-if="item.show">
            <li v-for="children in item.children" :key="children">
              <h1 v-on:click="children.show = !children.show">
                {{children.name}}
                
              </h1>
              <ul class="side-items">
              <ul v-if="children.show">
                <li v-for="children in children.next" :key="children">
                  <h1>
                    {{children.name}}
                    
                  </h1>
                
                </li>
                
              </ul>
              </ul>
            </li>
            </ul>
          </ul>
        </li>
      </ul>
       
      </body>
    </template>
    
    <script>

import jsonData from '/js/jsonData.json'
export default{
  data(){
    return{
     data:jsonData
    }
  }
}
    </script>
    