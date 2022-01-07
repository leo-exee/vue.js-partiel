<template>
  <div class="app">
    <h1>VideoStore</h1>

    <router-link to="/videos" class="return">◂◂ Retour</router-link><br><br>

    <section v-for="item in videoList"
      :key="item.name">
      <VideoDetail v-if="item.id == id" :item="item" />
    </section>
    
    <footer class="footer">
      <p>{{ copyright }}</p>
    </footer>
  </div>
</template>

<script>
import VideoDetail from "../components/VideoDetail.vue";

export default {
  name: "app",
  components: {
    VideoDetail,
  },
  data() {
    return {
      id: this.$route.params.name,
      videoList: [
        {
          id:'0',
          name: "Vidéo de chat",
          price: 25,
          image: {
            source: "assets/cat.jpg",
          },
          new: true,
          coomingSoon: false
        },
        {
          id:'1',
          name: "Test",
          price: 0.45,
          image: {
            source: "assets/NeonDrive.jpg",
          },
          new: true,
          coomingSoon: false
        },
        {
          id:'2',
          name: "How to make money when you are student in 2021",
          price: 5.99,
          image: {
            source: "assets/joris.jpg",
          },
          new: false,
          coomingSoon: false
        },
        {
          id:'3',
          name: "Social Game",
          price: 15,
          image: {
            source: "assets/nico.jpg",
          },
          new: false,
          coomingSoon: false
        },
        {
          id:'4',
          name: "YouTube rewind 2021",
          price: 'Gratuit',
          image: {
            source: "assets/yt.jpg",
          },
          new: false,
          coomingSoon: true
        },
        {
          id:'5',
          name: "Revenge (CREEPER AWW MEN)",
          price: 999.99,
          image: {
            source: "assets/creeper.jpg",
          },
          new: false,
          coomingSoon: false
        },
        {
          id:'6',
          name: "Bebou 🥺 ?",
          price: 9500,
          image: {
            source: "assets/bebou.jpg",
          },
          new: true,
          coomingSoon: false
        },
      ],
    };
  },
  computed: {
    copyright() {
      const currentYear = new Date().getFullYear();
      return `Copyright VideoStore ${currentYear}`;
    },
  },
  methods: {
  },
};
</script>

<style lang="scss">
.return {
  widows: 100%;
  font-weight: bold;
  text-decoration: none;
}
.return {
  a:hover {
    text-decoration: underline;
  }
}
</style>


      