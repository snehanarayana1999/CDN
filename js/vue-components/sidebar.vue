<template>
  <link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined" rel="stylesheet" />
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
             <span v-if="children.next" class="material-symbols-outlined">arrow_drop_down</span>
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
var json = '[{"id": 1,"name": "GENERAL", "show": false, "children": [{ "name": "Cloud Storage","show": false,"next": [{ "name": "Signin"    }, { "name": "Signout" }, { "name": "Logoff" }]}, { "name": "Customers", "show": false, "next": [{  "name": "Signin"}, { "name": "Signout" }, { "name": "Logoff" }]  } ] }, { "id": 2,"name": "ADMINISTRATION","show": false,"children": [{"name": "Team Settings","show": false,"next": [{ "name": "Login"}, { "name": "LogOut" }, { "name": "Logoff" }]}, { "name": "Team Managers" }]},{"id": 3,"name": "INVITATIONS","show": false,"children": [{ "name": "Members","show": false, "next": [{   "name": "Login" }, { "name": "LogOut" }, { "name": "Logoff" }]}, { "name": "Plugin" }] },{"id": 4,"name": "PAYMENTS","show": false,"children": [{ "name": "About" }, { "name": "Password" }] },{"id": 5,"name": "SETTINGS","show": false,"children": [{ "name": "Messages" }, { "name": "Overview" }]}]'
var jsonData = JSON.parse(json)
export default{
  data(){
    return{
     data:jsonData
    }
  }
}
    </script>
    <style scoped>
    .sidebar{
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
      margin-top:10px;
      font-size: 14px;
      margin-left: 70px; 
      color:gray;
      position:absolute;
      padding:5px;
      
    }
      
    .side-menu{
      margin-left: 10px; 
      color: black;
      padding: 5px;
     }
     
    .side-menu h1{
      font-weight:bold;
      padding: 5px;
      }
      
    .side-menu h1:hover {
      background-color: transparent;
      color: #276cda;
    }
    .side-items{
      margin-left: 30px; 
      }
      
    </style>
    
