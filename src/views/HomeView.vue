<template>
    <HelloWorld :searchResults= "searchResults" @sendsearchResult="sendsearchResult($event)"/>
</template>
<script>
import HelloWorld from '@/components/HelloWorld.vue'
export default {
  name: 'HomeView',
  props: ['searchResults'],
  components: {
    HelloWorld
  },
  // data () {
  //   return {
  //     sendsearchResultTo: {}
  //   }
  // },
  methods: {
    sendsearchResult (e) {
      console.log('In the homeview')
      console.log(e)
      // this.sendsearchResultTo = e
      // this.$emit('sendsearchResult', sendsearchResultTo)
    }
  }
}
</script>
