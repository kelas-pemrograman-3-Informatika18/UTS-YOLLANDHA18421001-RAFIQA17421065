<template>
  <q-page class="bg-pink-11">
    <div class="row">
      <q-card class="fixed-center col-md-4 col-xs-12 bg-white" flat>
        <q-card-section>
          <div class="text-h6 q-pb-md">
            Welcome! Happy Shopping, Happy US
          </div>
          <img
      alt="Logo FIQYOL"
      src="~assets/logo.png"
      align="right"
    >
          <q-form
            @submit="onSubmit"
            @reset="onReset"
            class="q-gutter-md"
          >
            <q-input
              filled
              v-model="username"
              label="Your Username"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Input Your Username']"
            />

            <q-input
              filled
              type="password"
              v-model="password"
              label="Your Password, not PasPort wkwk"
              lazy-rules
              :rules="[
                val => val !== null && val.length > 0 || 'Password cant be empty'
              ]"
            />
            <div class="q-gutter-md">
              <q-btn label="Login" type="submit" color="primary"/>
              <q-btn label="Register" to="/register" flat color="red"/>
              <!--<q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />-->
            </div>
        </q-form>
        </q-card-section>
    </q-card>
    </div>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'fiqyol' && this.password === '12345') {
        this.$q.notify({
          type: 'positive',
          message: 'Welcomeee'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'failed, your Username/Password are wrong'
        })
      }
    },
    onReset () {
      this.username = null
      this.password = null
    }
  }
}
</script>
