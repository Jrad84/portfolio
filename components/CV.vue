<template>
<v-container>
      <v-row class="mt-12">
            
            <v-col
                 
                  cols="12"
                  class="pa-4"
                  fluid="true"
            >
               <v-card
                class="mx-auto"
                max-width="1244"
              >
              <v-row>
              <v-col>
                <div>
                  <img
                      
                      loading="lazy"
                     
                      :src="`${item.image}`"
                  />
               </div>
              </v-col>
              <v-col>
                 <v-card class="mr-1" color="#0a75ad" >
                    <v-card-title>
                        {{item.title}} 
                        
                    </v-card-title>
                  
         

                        <v-card-text style="color:white">
                          {{item.description}}
                        </v-card-text>
                        <v-row>
                      <div v-for="link in item.links" :key="link">
                        
                        <v-btn 
                          x-small 
                          class="mt-4 ml-12"
                          max-height="200px"
                          color="#0a75ad"
                         
                          >
                          {{link}}</v-btn>
                      
                      </div>
                        </v-row>
                      <v-chip
                          class="ma-2 mt-10"
                          color="#47539b"
                          v-for="t in item.tech" :key="t"
                        >
                          {{t}}
                        </v-chip>
                 
                </v-card>
              </v-col>
              </v-row>
            </v-card>
          </v-col>
      </v-row>
</v-container>
</template>

<script>
export default {
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