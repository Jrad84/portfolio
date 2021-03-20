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
              
                   <v-card-text>
                    <div class="d-flex justify-center"><h3>Interests outside tech</h3></div>
                    <p class="text--primary">
                        Amateur Astronomy
                    </p>
                   </v-card-text>
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
                                max-height="400"
                                 height="auto"
                                width="100%"
                                :src="scope"
                            />
                                <!-- <v-img
                                :max-width="width"
                                max-height="500"
                                height="auto"
                                width="100%"
                                :src="`${kartclass.image1}`"
                            /> -->
                         </v-row>
                 </v-card>
              </v-col>
               </div>
            </v-card>
              <v-card >
                     
              
                  
                    <div  class="d-flex align-content-start">
                        <v-card-text id="text"  class="d-flex flex-wrap mt-2">
                            
                        
                    
                         <v-row class="d-flex justify-center mx-2 mb-2 mt-6">
                      
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
import Scope from "~/assets/scope.jpg"
export default {
    data() {
        return{
            scope: Scope
        }
    },
    components: {Scope}
}
</script>