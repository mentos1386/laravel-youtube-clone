<template>
  <div class="card card-outline-primary" >
    <router-link :to="{ name: 'Video', params: { id } }">
      <img class="card-img-top img-fluid" src="data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%22318%22%20height%3D%22180%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%20318%20180%22%20preserveAspectRatio%3D%22none%22%3E%3Cdefs%3E%3Cstyle%20type%3D%22text%2Fcss%22%3E%23holder_15c4afca955%20text%20%7B%20fill%3Argba(255%2C255%2C255%2C.75)%3Bfont-weight%3Anormal%3Bfont-family%3AHelvetica%2C%20monospace%3Bfont-size%3A16pt%20%7D%20%3C%2Fstyle%3E%3C%2Fdefs%3E%3Cg%20id%3D%22holder_15c4afca955%22%3E%3Crect%20width%3D%22318%22%20height%3D%22180%22%20fill%3D%22%23777%22%3E%3C%2Frect%3E%3Cg%3E%3Ctext%20x%3D%22117.015625%22%20y%3D%2297.2%22%3E318x180%3C%2Ftext%3E%3C%2Fg%3E%3C%2Fg%3E%3C%2Fsvg%3E" alt="Card image cap">
    </router-link>

    <div class="card-block">

      <h5 class="card-title">
        <router-link :to="{ name: 'Video', params: { id } }" class="link-to-video">{{ title }}</router-link>
      </h5>

      <p class="card-text"><small class="text-muted">Uploaded {{ createdAt }}</small></p>

    </div>
  </div>
</template>

<script>
  export default {
    name: 'video',
    props: ['video'],
    data: function () {
      return {
        id: this.video.id,
        title: this.video.title,
        description: this.video.description,
        file: this.video.file,
        categories: this.video.categories,
        createdAt: this.video.created_at
      }
    }
  }
</script>

<style lang="sass" scoped>
  @import '../assets/sass/colors'

  .link-to-video
    color: $text-dark-primary
    text-decoration: none !important

</style>
