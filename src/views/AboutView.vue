<template>
  <div class="about">
    <h1>{{ sendSearchResult.artistName }}</h1>
  </div>
</template>

<script>
export default {
  props: ['sendSearchResult'],
  data () {
    return {
      result: {}
    }
  },
  created () {
    console.log('this is in created')
    console.log(this.sendSearchResult.artistName)
  }
}
</script>
