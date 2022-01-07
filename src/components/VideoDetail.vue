<template>
  <div>
      <img width="75%"
        :src="item.image.source"
      />
      <div>
        <h2>{{ item.name }}</h2>
        <h4 v-if="item.new" class="tag">Nouveauté</h4>
        <h4 v-if="item.coomingSoon">Prochainement</h4>
        <div v-else>
          <h2>{{ item.price }} €</h2>
          <button>Acheter</button>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: "videoItem",
  props: ["item"]
};
</script>

<style lang="scss">
button {
  border: 3px solid #42b983;
  color:#42b983;
  padding: 10px 20px;
  font-size:25px;
  border-radius: 50px;
  background-color: #ffffff00;
  cursor: pointer;
  transition: background 0.2s;
}
button:hover {
  border: 3px solid #42b983;
  color:#fff;
  padding: 10px 20px;
  font-size:25px;
  border-radius: 50px;
  background-color: #42b983;
}
</style>
