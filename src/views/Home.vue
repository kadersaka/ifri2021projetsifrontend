<template>
  <div class="q-pa-md">
   <div class="row q-col-gutter-md">
    <div class="col-4">
      <q-card class="my-card bg-purple text-white">
      <q-card-section>
        <div class="text-h6">PORTEFEUILLE</div>
        <div class="text-subtitle2">500.000 FCFA</div>
      </q-card-section>

      <q-card-actions>
        <q-btn flat>Recharger</q-btn>
      </q-card-actions>
    </q-card>
    </div>
        <div class="col-4">
      <q-card class="my-card bg-purple text-white">
      <q-card-section>
        <div class="text-h6">IINSCRIPTIPONS</div>
        <div class="text-subtitle2"></div>
      </q-card-section>

      <q-card-actions>
        <q-btn flat>Consulter</q-btn>
      </q-card-actions>
      
    </q-card>
    
    </div>
        <div class="col-4">
          <q-card class="my-card q-py-sm">
            <q-item>
              <q-item-section>
                <q-btn color="light-blue-8" icon="fab fa-facebook-f" label="Share with facebook" />
              </q-item-section>
              <q-item-section avatar>
                <q-btn flat round color="grey-6" icon="fas fa-times" size="sm" />
              </q-item-section>
            </q-item>
            <q-item>
              <q-item-section>
                <q-btn color="grey-6" icon="fab fa-twitter" text-color="black" label="Tweet with twitter" outline />
              </q-item-section>
              <q-item-section avatar>
                <q-btn flat round color="grey-6" icon="fas fa-times" size="sm" />
              </q-item-section>
            </q-item>
            <q-item>
              <q-item-section>
                <q-btn color="grey-6" icon="fab fa-pinterest-p" text-color="black" label="Save with pinterest" outline />
              </q-item-section>
              <q-item-section avatar>
                <q-btn flat round color="grey-6" icon="fas fa-times" size="sm" />
              </q-item-section>
            </q-item>
          </q-card>
        </div>

   </div>

   <q-toolbar>
     <q-toolbar-title><strong>Actualité</strong></q-toolbar-title>
     <q-btn color="dark" icon-right="fas fa-chevron-down" label="Dernières minutes" flat />
   </q-toolbar>
   <div class="row q-col-gutter-md">
     <div class="col-3">
       <q-card class="my-card">
         <q-img src="1.jpg">
           <div class="absolute-bottom">
             <div class="text-subtitle1">Marketing Landing page</div>
             <div class="text-subtitle2">03 August 2018</div>
           </div>
         </q-img>
       </q-card>
     </div>
     <div class="col-3">
       <q-card class="my-card">
         <q-img src="2.jpg">
           <div class="absolute-bottom">
             <div class="text-subtitle1">Community Dashboard</div>
             <div class="text-subtitle1">03 August 2018</div>
           </div>
         </q-img>
       </q-card>
     </div>
     <div class="col-3">
       <q-card class="my-card">
         <q-img src="3.jpg" height="156px">
           <div class="absolute-bottom">
             <div class="text-subtitle1">Movie Booking App</div>
             <div class="text-subtitle2">03 August 2018</div>
           </div>
         </q-img>
       </q-card>
     </div>
     <div class="col-3">
       <q-card class="my-card">
         <q-img src="4.png" height="156px">
           <div class="absolute-bottom">
             <div class="text-subtitle1">Pattern Grandients</div>
             <div class="text-subtitle2">03 August 2018</div>
           </div>
         </q-img>
       </q-card>
     </div>
   </div>
  </div>
</template>

<script>


export default {
  name: 'Home',
 data: () => ({
   value: 0
 })
}
</script>
