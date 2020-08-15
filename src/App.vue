<template>

  <div id="app" class="container">
    <nav>
      <ul>
        <li><router-link to="/">VueFirebase</router-link></li>
      </ul>
      <ul>
        <li v-if="!addpost"><router-link to="/addpost">New Post</router-link></li>
      </ul>
    </nav>

   <router-view></router-view>
  </div>

</template>

<script>
  export default {
    name: "App",
    data(){
      return {
        addpost: false
      }
    },
    watch: {
      "$route": {
        handler: function(to){
          if(to.path === "/addpost"){
           //console.log(to)
            this.addpost = true;
          }else{
            this.addpost = false;
          }

        },
       immediate: true
      }
    }
  }

</script>
