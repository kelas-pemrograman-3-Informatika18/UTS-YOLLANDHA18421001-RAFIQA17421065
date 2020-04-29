<template>
    <q-page padding>
        <q-card flat >
            <q-card-section class="q-gutter-md">
                <div class="text-h5">Form to Shoppingg</div>
                <q-form
                @submit="onSubmit"
                @reset="onReset"
                class="q-mt-lg"
                >
                    <div class="q-gutter-md">
                        <q-input label="Clothes" v-model="clothes" filled :rules="[ val => val && val.length > 0 || 'Input Clothes Please']"></q-input>
                        <q-input label="Size" v-model="size" filled :rules="[ val => val && val.length > 0 || 'Input Size Please']"></q-input>
                        <q-input label="Color" v-model="color" filled :rules="[ val => val && val.length > 0 || 'Input Color Please']"></q-input>
                        <q-input label="Price" v-model="price" filled :rules="[ val => val && val.length > 0 || 'Input Price Please']"></q-input>
                        <q-input label="Number" v-model="number" filled :rules="[ val => val && val.length > 0 || 'Input Number Please']"></q-input>
                        <q-input label="Informations" v-model="informations" filled :rules="[ val => val && val.length > 0 || 'Input Informations Please']"></q-input>
                        <q-input label="Payment" v-model="payment" filled :rules="[ val => val && val.length > 0 || 'Input Payment Please']"></q-input>
                        <q-btn type="submit" label="Input" color="grey" unelevated></q-btn>
                        <q-btn type="reset" label="Reset" color="grey" flat unelevated></q-btn>
                    </div>
                </q-form>
            </q-card-section>
        </q-card>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      clothes: null,
      size: null,
      color: null,
      price: null,
      number: null,
      informations: null,
      payment: null
    }
  },
  methods: {
    onReset () {
      this.clothes = null
      this.size = null
      this.color = null
      this.price = null
      this.number = null
      this.informations = null
      this.payment = null
    },
    onSubmit () {
      this.$q.notify({
        type: 'positive',
        message: 'Succeesssss uyy'
      })
      this.$router.push({ name: 'list' })
    }
  }
}
</script>
