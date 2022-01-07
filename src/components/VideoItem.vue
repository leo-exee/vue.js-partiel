
<template>
  <div>
    <h4 v-if="item.new" class="tag">Nouveauté</h4>
    <h4 v-if="item.coomingSoon" class="tag">Prochainement</h4><br>
    <img width="50%" :src="item.image.source" />
    <h3>
      <router-link
        :to="{ name: 'Video', params: { name: item.id } }"
        :item="item"
        >{{ item.name }}</router-link
      >
    </h3>
  </div>
</template>

<script>
export default {
  name: "videoItem",
  props: ["item"],
};
</script>
