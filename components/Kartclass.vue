<template>
<no-ssr>
<v-container>
    <div >
      <v-row class="mt-12">
            <v-col
                  fluid="true"
            >
               <v-card
               id="parent"
                class="d-flex align-content-start"
              >
              <v-col >
                  <v-img
                    :max-width="width"
                    max-height="500"
                    height="auto"
                    width="100%"
                    :src="`${kartclass.image1}`"
                  />
              </v-col>
             <div class="d-sm-none d-none d-md-flex">
              <v-col >
                 <v-card 
                    id="child1"
                     >
                         <v-row>
                            <v-img
                                class="mt-3 mr-2"
                                max-width="365"
                                max-height="360"
                                 height="auto"
                                width="100%"
                                :src="`${kartclass.image2}`"
                            />
                         </v-row>
                 </v-card>
              </v-col>
               </div>
            </v-card>
              <v-card >
                     
                <v-row class="d-flex justify-center">
                        <div v-for="link in kartclass.links" 
                            :key="link" 
                        >
                        <v-btn 
                          small 
                          class="mt-4 ml-12"
                          max-height="200px"
                          color="#0a75ad"
                          @click="goTo(link)"
                          >
                          {{link}}
                          </v-btn>
                      </div>
                      </v-row>
                  
                    <div  class="d-flex align-content-start">
                        <v-card-text id="text"  class="d-flex flex-wrap mt-2">
                            
                         {{kartclass.description}}
                    
                         <v-row class="d-flex justify-center mx-2 mb-2 mt-6">
                        <v-chip
                          id="chip"
                          class="pa-4 mx-8"
                          color="#47539b"
                          v-for="t in kartclass.tech" :key="t"
                        >
                          {{t}}
                        </v-chip>
                         </v-row>
                          </v-card-text>
                    </div>
                </v-card>
          </v-col>
          
      </v-row>
    </div>
</v-container>
</no-ssr>
</template>

<script>


export default { 
   props: ["kartclass", "goTo"],
  computed: {
      width () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return 450
          case 'sm': return 400
          case 'md': return 500
          case 'lg': return 750
          case 'xl': return 800
        }
      },
     
    },
   


}
</script>

<style scoped>

</style>