<template>
  <div class="breadcrumbs">
    <router-link to="/main" class="text-white">Вернуться к списку</router-link>
  </div>
  <div class="card" v-if="personInfo">
    <div>
      <p><strong>Фамилия:</strong> {{ personInfo.last_name }}</p>
      <p><strong>Имя:</strong> {{ personInfo.first_name }}</p>
      <p><strong>"Электронная почта:</strong> {{ personInfo.email }}</p>
    </div>
    <div>
      <img src="#" :title="`${personInfo.first_name}'s avatar`">
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "view",
  mounted () {
    this.$store.dispatch('detailsUser', this.$route.params.id)
  },
  computed: {
    ...mapGetters({
      personInfo: 'personInfo'
    })
  }
}
</script>
