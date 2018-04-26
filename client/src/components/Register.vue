<template>
  <div class="Mantap">
    <h1>Register</h1>
    <input type="email" name="email" v-model="email" placeholder="Masukan Email"/><br>
    <input type="password" name="password" v-model="password" placeholder="Masukan Password"/><br>
    <button 
      @click="register">
      Register
    </button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationServices'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },  
  methods: {
    async register () {
      await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.mantap{
  height: 100px;
  widows: 100px;
}
</style>


<!-- // watch: {
  //   email (value){
  //     console.log("email has changed", value)
  //   }
  // },
  // mounted (){
    //   setTimeout( ()=>{
    //     this.email = "Cuk"
    //   }, 1000)
    // } -->