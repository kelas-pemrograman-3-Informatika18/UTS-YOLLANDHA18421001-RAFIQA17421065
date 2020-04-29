<template>
  <q-page class="bg-brown-3">
    <div class="row">
      <q-card class="fixed-center col-md-4 col-xs-12 bg-deep-orange-11" flat>
        <q-card-section>
          <div class="text-h6 q-pb-md">
            Please Regist Before SHopping
          </div>
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
              :rules="[ val => val && val.length > 0 || 'Input Your New Username']"
            />
            <q-input
              filled
              v-model="name"
              label="Your Name"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Input Your Name']"
            />
            <q-input
              filled
              v-model="address"
              label="Your Address"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Input Your Address']"
            />
            <q-input
              filled
              v-model="handphone"
              label="Your Handphone Number"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Input Your Handphone Number']"
            />
            <q-input
              filled
              v-model="email"
              label="Your Email"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Input YOur Email']"
            />

            <q-input
              filled
              type="password"
              v-model="password"
              label="YOur Password"
              lazy-rules
              :rules="[
                val => val !== null && val.length > 0 || 'Password cant be empty'
              ]"
            />
            <div class="q-gutter-md">
              <q-btn label="Register" type="submit" color="primary"/>
              <q-btn label="Login" to="/" flat color="red"/>
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
      password: null,
      name: null,
      email: null,
      address: null,
      handphone: null
    }
  },
  methods: {
    onSubmit () {
    },
    onReset () {
      this.username = null
      this.password = null
    }
  }
}
</script>
