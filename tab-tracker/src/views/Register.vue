<template>
  <div>
    <h1>
        Register
    </h1>
    <input 
    type="email"
    name="email"
    v-model="email"
    placeholder="email" />
    <br>
    <input 
    type="password"
    name="password"
    v-model="password"
    placeholder="password" />
  </div>
  <br>
  <button @click="register"> 
  Register 
  </button>
</template>

<script>
import AuthenicationService from '@/services/AuthenticationService'
export default ({
    data() {
        return{
            email:'',
            password:''
        }
    },
    methods: {
        async register(){
            const response = await AuthenicationService.register({
                email:this.email,
                password:this.password
            })
           console.log(response.data)
        }
    }
})
</script>

<style>
</style>