<template>
  <div class="container">
    <div class="card card-inverse card-profile">
      <div class="card-block">
        <h1 class="card-title display-4">
          <img :src="profile.avatar" class="rounded rounded-circle avatar-image img-thumbnail"/>
          {{ profile.name }}
        </h1>
      </div>
    </div>

    <div class="card-columns">
      <list-video v-for="video in profile.videos" :key="video.id" :video="video"></list-video>
    </div>

  </div>
</template>

<script>
  import { getProfile } from 'src/api/user'
  import { mapGetters } from 'vuex'
  import ListVideo from 'src/components/ListVideo'

  export default {
    name: 'profile',
    computed: {
      ...mapGetters(['profile'])
    },
    components: {
      ListVideo
    },
    mounted () {
      getProfile()
    }
  }
</script>

<style lang="sass" scoped>
  @import "../assets/sass/colors"

  .card-profile
    background: $cyan-500
    border-color: $cyan-500
    margin-bottom: 2em
    margin-top: 2em

    .card-title
      margin-bottom: 0

  .avatar-image
    height: 10.5rem
    width: 10.5rem

</style>
