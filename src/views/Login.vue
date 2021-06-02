<template>
  <div class="q-pa-md" style="max-width: 400px">

<q-card square bordered class="q-pa-lg shadow-1">
        <q-form
        @submit="onSubmit"
        @reset="onReset"
        class="q-gutter-md"
        >
    <q-card-section>

        <q-input
            filled
            v-model="email"
            label="Your email *"
            hint="Votre email"
            lazy-rules
            :rules="[val => !!val || 'Email is missing', isValidEmail]"
        />

        <q-input
            filled
            type="password"
            v-model="pass"
            label="Mot de passe *"
            lazy-rules
            :rules="[ val => val && val.length > 7|| 'Mot de passe réquis']"
        />


        <q-checkbox class="text-grey-8" dense v-model="remember_me" label="Remember me"/>
    </q-card-section>

<q-card-actions class="q-px-md">
        <div>
            <q-btn label="Submit" type="submit" color="primary"/>
            <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
        </div>
</q-card-actions>   

<q-card-section class="text-center q-pa-none">
            <p class="text-grey-6">Nouveau à l'UAC? Créez un compte</p>
</q-card-section>    
</q-form>

</q-card>

  </div>
</template>

<script>
export default {
    name: 'Login',

  data () {
    return {
      email: null,
      pass: null,
      remember_me: false
    }
  },

  methods: {
    onSubmit () {
      if (this.accept !== true) {
        this.$q.notify({
          color: 'red-5',
          textColor: 'white',
          icon: 'warning',
          message: 'You need to accept the license and terms first'
        })
      }
      else {
        this.$q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: 'Submitted'
        })
      }
    },
    isValidEmail (val) {
      const emailPattern = /^(?=[a-zA-Z0-9@._%+-]{6,254}$)[a-zA-Z0-9._%+-]{1,64}@(?:[a-zA-Z0-9-]{1,63}\.){1,8}[a-zA-Z]{2,63}$/;
      return emailPattern.test(val) || 'Invalid email';
    },

    onReset () {
      this.email = null
      this.pass = null
      this.remember_me = false
    }
  }
}
</script>
<style>

</style>