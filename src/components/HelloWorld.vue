<template>
  <div class="profile-container" v-for="(searchResult,i) in searchResults.slice(0,3)" :key="i">
      <div class="profile-content">
        <div class="profile-header">
          <img id="avatar" src="{{searchResult.artworkUrl30}}" alt="artwork">
          <div class="profile-info-wrapper">
            <div class="profile-name">
              <h2 id="name">{{searchResult.artistName}}</h2>
              <p id="user">{{searchResult.artistId}}</p>
            </div>
            <!-- <router-link id="date" to="/about">Details</router-link> -->
          </div>
        </div>
        <p id="bio">{{searchResult.collectionCensoredName}}</p>
        <div class="profile-stats-wrapper">
          <div class="profile-stat">
            <p class="stat-title">Kind</p>
            <p id="repos" class="stat-value">{{searchResult.kind}}</p>
          </div>
          <div class="profile-stat">
            <p class="stat-title">Track Name</p>
            <p id="repos" class="stat-value">{{searchResult.trackName}}</p>
          </div>
          <div class="profile-stat">
            <p class="stat-title">Track Number</p>
            <p id="followers" class="stat-value">{{searchResult.trackNumber}}</p>
          </div>
          <div class="profile-stat">
            <p class="stat-title">Track Price</p>
            <p id="following" class="stat-value">${{searchResult.trackPrice}}</p>
          </div>
        </div>
        <!-- <div class="profile-bottom-wrapper">
          <div class="profile-info">
            <div class="bottom-icons"><img src="@/assets/icon-location.svg" alt=""></div>
            <p id="location"></p>
          </div>
          <div class="profile-info">
            <div class="bottom-icons"><img src="@/assets/icon-website.svg" alt=""></div>
            <p id="page"></p>
          </div>
          <div class="profile-info">
            <div class="bottom-icons"><img src="@/assets/icon-twitter.svg" alt=""></div>
            <p id="twitter"></p>
          </div>
          <div class="profile-info">
            <div class="bottom-icons"><img src="@/assets/icon-company.svg" alt=""></div>
            <p id="company"></p>
          </div>
        </div> -->
      </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['searchResults'],
  data () {
    return {
      sendSearchResult: {}
    }
  },
  methods: {
    send (searchResult) {
      this.sendSearchResult = {
        artistName: searchResult.artistName
      }
      console.log(this.sendSearchResult)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
/* body {
  height: 405vh;
} */
</style>
