<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
    import { getSeller } from 'api'
export default {
  data(){
    return{

    }
  },
  created(){
  this._getSeller()
  },
  methods:{
   _getSeller() {
        getSeller({
          // id: this.seller.id
        }).then((seller) => {
           console.log(seller)
          // this.seller = Object.assign({}, this.seller, seller)
        })
      }
  }
}
</script>


<style lang="stylus">
#app
  font-family Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  margin-top 60px
</style>
