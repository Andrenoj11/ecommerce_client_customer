<template>
    <section>
    <div class="container">
      <div class="row" style="min-height: 700px">
        <div class="col-md d-flex justify-content-center align-items-center">
          <div class="card text-center">
            <div class="card-header">
              <ul class="nav nav-tabs card-header-tabs">
                <li class="nav-item">
                  <a @click.prevent="login" class="nav-link" href="">Log In</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link active" href="">Register</a>
                </li>
              </ul>
            </div>
            <div class="card-body">
              <form @submit.prevent="register">
                <div class="form-group text-left">
                  <label for="exampleInputEmail1">Email address</label>
                  <input
                    type="email"
                    class="form-control"
                    v-model="email"
                    aria-describedby="emailHelp"
                  />
                  <small id="emailHelp" class="form-text text-muted"
                    >We'll never share your email with anyone else.</small
                  >
                </div>
                <div class="form-group text-left">
                  <label for="exampleInputPassword1">Password</label>
                  <input
                    type="password"
                    class="form-control"
                    v-model="password"
                  />
                </div>
                <div class="text-left">
                  <button type="submit" class="btn btn-primary">Submit</button>
                </div>
              </form>
              <br />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'RegisterPage',
  components: {
  },
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login () {
      this.$router.push('/login')
    },
    register () {
      const obj = {
        email: this.email,
        password: this.password
      }
      this.$store.dispatch('register', obj)
    }
  }
}
</script>

<style>
</style>
