<template>
  <div class="app">
    <h1>VideoStore</h1>

    <h3>{{ address }}</h3>
    <h3>{{ email }}</h3>
    <h3>{{ phone }}</h3>

    <form action="" @submit="checkForm">
      <label for="name">Votre nom</label><br>
      <input id="name" v-model="name" type="text" name="name"><br><br>
      <label for="mail">Votre Email</label><br>
      <input id="mail" v-model="mail" type="mail" name="mail"><br><br>
      <label for="message">Votre Message</label><br>
      <textarea id="message" v-model="message" name="message" rows="5"></textarea><br>
      <button>Envoyer</button>
    </form>

    <footer class="footer">
      <p>{{ copyright }}</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "contact",
  data() {
    return {
      name: null,
      mail: null,
      message: null,
      address: "325 route de la buse, Avignon, France",
      email: "contact@video-store.com",
      phone: "01 32 84 32 00",
    };
  },
  computed: {
    copyright() {
      const currentYear = new Date().getFullYear();
      return `Copyright VideoStore ${currentYear}`;
    },
  },
  methods: {
    checkForm: function (e) {
      if (this.name && this.mail && this.message) {
        alert("Message envoyé");
        return true;
      }
      if (!this.name) {
        alert("Nom non valide");
      }
      if (!this.mail) {
        alert("Email non valide");
      }
      if (!this.message) {
        alert("Message non valide");
      }
      e.preventDefault();
    },
  },
};
</script>

<style lang="scss">
input, textarea {
  width: 50%;
}
</style>