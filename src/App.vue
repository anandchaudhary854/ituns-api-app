<template>
  <div class="searchbar-container">
    <!-- <label for="name">Enter search item: </label> -->
      <input v-model="searchItem" type="text" id="input" name="name" placeholder="Search Artist Name..." required>
      <button class="btn-search" id="submit" @click="callAPI">Search</button>
  </div>
  <router-view v-if="showResults" :searchResults= "searchResults"/>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      searchItem: '',
      searchResults: [],
      showResults: false
    }
  },
  methods: {
    async callAPI () {
      console.log(this.searchItem)
      try {
        const res = await axios.get(`https://itunes.apple.com/search?term=${this.searchItem}`)
        console.log(this.searchResults)
        this.searchResults = res.data.results
        console.log(this.searchResults)
        this.showResults = true
      } catch (err) {
        console.log(err)
      }
    },
    toggleSearchResults () {
      this.showResults = !this.showResults
    }
  }
}
</script>
