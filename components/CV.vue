<template>
<no-ssr>
<v-container>
    <div class="col-xs-4 d-sm-block center-md">
      <v-row class="mt-12">
            <v-col
                  class="pa-4"
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
                    :src="`${item.image1}`"
                  />
                
              </v-col>
               <div class="d-sm-none d-none d-md-flex">
               <v-col >
                  <v-img
                    :max-width="width"
                    max-height="510"
                    height="auto"
                    width="100%"
                    :src="`${item.image2}`"
                  />
                
              </v-col>
               </div>
              
            </v-card>
           
              <v-card>
                     
                <v-row class="d-flex justify-center pa-2">
                        <div v-for="link in item.links" 
                            :key="link" 
                        >
                        <v-btn 
                          small 
                          class="mt-4 ml-12"
                          max-height="200px"
                          color="#0a75ad"
                          @click="followLink(link)"
                          >
                          {{link}}</v-btn>
                      </div>
                      </v-row>
                  
                   <div  class="d-flex align-content-start">
                        <v-card-text id="text"  class="d-flex flex-wrap">
                            
                         {{item.description}}
                    
                         <v-row class="d-flex justify-center mx-2 mb-2 mt-6">
                        <v-chip
                          id="chip"
                          class="pa-4 mx-8"
                          color="#47539b"
                          v-for="t in item.tech" :key="t"
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
    computed: {
      width () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return 300
          case 'sm': return 400
          case 'md': return 500
          case 'lg': return 550
          case 'xl': return 800
        }
      },
     
    },
    props:["item"]
}
</script>
<style scoped>
img {
 
   max-height: 350px;
  max-width: 400;
  min-width: 100%;
  min-height: 350px;
}
</style>