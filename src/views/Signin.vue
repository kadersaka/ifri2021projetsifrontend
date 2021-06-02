<template>
  <q-layout>
    <q-page-container>
      <q-page class="flex flex-center" style="font-family: Lato;">
<!--        <div id="particles-js"></div>-->
        <q-card :style="$q.platform.is.desktop ? 'width:55%;' : ''" class="row my-card items-center q-pa-none q-ma-none shadow-24">
          <q-card-section v-if="$q.platform.is.desktop" class="col-md-4 col-lg-4 col-sm-12 sol-xs-12 items-center float-left" style="background-color: #1f509e"
                          :style="{'height':(win_height-270)+'px'}" horizontal>
            <div class="text-center full-width">
              <div><img src="images/logo.png" style="width: 33%"/></div>
              <div class="text-weight-bolder text-white text-h6">PORTAIL WEB</div>
              <div class="text-caption text-white">UNIVERSITE D'ABOMEY-CALAVI</div>
            </div>
          </q-card-section>
          <q-card-section class="col-md-8 col-lg-8 col-sm-12 sol-xs-12 float-left">
            <q-card-section class="items-center">
              <div>
                <div v-if="!$q.platform.is.desktop" class="text-weight-bolder text-center q-mb-md text-primary text-h6">Quasar Shopping</div>
                <q-form         
                @submit="onSubmit"
                @reset="onReset"
                :style="$q.platform.is.desktop ? 'width:55%;margin: auto;' : 'margin: auto;'" class="q-gutter-md">
                  <span class="text-subtitle1 text-weight-bold text-grey-7">Page de connexion</span>
                  <q-input
                    dense
                    outlined
                    type="email"
                    v-model="email"
                    label="Email"
                    lazy-rules
                    :rules="[val => !!val || 'Email is missing', isValidEmail]"
                  />

                  <q-input
                    dense
                    type="password"
                    outlined
                    v-model="pass"
                    label="Pass"
                    lazy-rules
                    :rules="[ val => val && val.length > 7|| 'Mot de passe réquis']"
                  />
                  <div>
                    <q-checkbox class="text-grey-8" dense v-model="remember_me" label="Se souvnir de moi"/>

                    <q-btn class="text-capitalize" size="sm" style="width:75px" dense label="Connexion" to="/" type="button" color="primary"/>
                  </div>

                    <q-card-section class="text-center q-pa-none">
                                <span class="text-grey-6">Nouveau à l'UAC?</span>
                                <q-btn class="float-right text-blue-9 text-capitalize" size="sm" style="width:75px;border: 1px solid #36669e;" dense label="Inscription" type="button"/>

                    </q-card-section>   
                </q-form>

              </div>
            </q-card-section>
          </q-card-section>

        </q-card>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script>
    export default {
        name:'Signin',
        data() {
            return {
                email: null,
                password:  null,
                remember_me: false
            }
        },
        mounted() {
        },
        computed: {
            win_width() {
                return this.$q.screen.width - 59;
            },
            win_height() {
                return this.$q.screen.height - 0;
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
  .my-card {
    /*width: 55%;*/
    height: 30%;
  }
  #particles-js {
    position: absolute;
    width: 100%;
    height: 100%;
    /*background: linear-gradient(145deg, #abbaab 15%, #ffffff 70%);*/
    /*background: linear-gradient(145deg,#f7f8f8 11%, #627e79 75%);*/
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 50% 50%;
  }
  .login-form {
    position: absolute;
  }
</style>