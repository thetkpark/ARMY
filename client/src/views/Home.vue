<template>
  <div class="home">
    <Navbar />
    <!-- <Carousels /> -->
    <v-container>
      <v-row>
        <v-col class="albumList" v-for="(data,index) in albums" :key="index" cols="4">
          <Album :data="data" />
        </v-col>
<<<<<<< HEAD
        <a href="/auth/google">Hello</a>
      </div>
        </v-row>
    </div>
=======
      </v-row>
>>>>>>> a765701b9a27c43e6833d70442970e2c5441a5f6
    </v-container>
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import Carousels from "../components/Carousels";
import Album from "../components/Album";
import axios from "../axios/axios.js";
// @ is an alias to /src
export default {
  data() {
    return {
      albums: [
        {
          name: "test1",
          img: "Photo/Mapof.jpg",
        },
        {
          name: "test2",
          img: "Photo/cool.jpeg",
        },
        {
          name: "test3",
          img: "Photo/face.jpg",
        },
        {
          name:"test4",
          img:"Photo/BTS-19.jpg",
        },
        {
          name:"test5",
          img:"Photo/skool.jpeg",
        },
        {
          name:"test6",
          img:"Photo/wings.webp",
        }
      ],
    };
  },
  components: {
    Navbar,
    Carousels,
    Album,
  },
  mounted(){
     axios.get("/current_user").then(response => {
       console.log(response.data);
     })
  }
};
</script>
<style scoped>
.home {
  width: 100vw;
  height: 100vh;
}
.albumList{
  padding: 5% 2%;
}
</style>