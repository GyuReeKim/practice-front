<template>
  <div>
    <div v-if="loading" class="spinner-border" role="status">
      <span class="sr-only">Loading...</span>
    </div>
    <div class="signup-div col-6 offset-3">
      <div class="form-group">
        <label for="id">ID</label>
        <input id="id" class="form-control" type="text" v-model="credential.username">
      </div>
      <div class="form-group">
        <label for="password1">PASSWORD</label>
        <input id="password1" class="form-control" type="password" v-model="credential.password1">
      </div>
      <div class="form-group">
        <label for="password2">PASSWORD 확인</label>
        <input id="password2" class="form-control" type="password" v-model="credential.password2">
      </div>
      <div class="form-group">
        <label for="email">PASSWORD</label>
        <input id="email" class="form-control" type="email" v-model="credential.email">
      </div>
      <button class="btn btn-primary" @click="signup">회원가입</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SignupForm',
  data: function(){
    return {
      credential: {
        username: '',
        password1: '',
        password2: '',
        email: ''
      },
      loading: false
    }
  },
  methods: {
    signup(){
      console.log('회원가입 시도!!!')
      axios.post('http://localhost:8000', this.credential)
      .then((res)=>{
        console.log(res)
        
      })
      .catch((error)=>{
        console.log(error)
      })
    }
  }
}
</script>

<style>

</style>