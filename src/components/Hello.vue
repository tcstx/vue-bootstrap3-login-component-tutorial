<template>
  <div class="hello">
    <login-component
      :errorMessage="errorMessage"
      v-on:loginCredentials="checkCredentials"
      passwordPattern=".{2,8}"
      passwordMessage="Greater than 1 and less than 9"
    ></login-component>
  </div>
</template>

<script>
  import LoginComponent from './LoginComponent.vue'
export default {
  name: 'hello',
  components: {
    LoginComponent,
    'login-component': LoginComponent
  },
  data () {
    return {
      errorMessage: ''
    }
  },
  methods: {
    checkCredentials: function (event) {
      console.log('Email is: ' + event.email)
      console.log('Password is: ' + event.password)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
