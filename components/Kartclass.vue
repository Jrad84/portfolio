<template>
<v-container d-flex>
      <v-row class="mt-12">
            
            <v-col
                  cols="12"
                  xs="1"
                  class="pa-4"
                  fluid="true"
            >
               <v-card
               id="parent"
                class="mx-auto"
                max-width="1244"
              >
             
              <v-col>
                <div>
                  <img
                    id="mainImg"
                      loading="lazy"
                      :src="`${kartclass.image1}`"
                  />
               </div>
              </v-col>
              <v-col>
                 <v-card 
                    id="child1"
                    class="mr-1"
                    
                     >
                     
                     <div class="mx-2">
                         <v-row>
                      <img
                      class="kcImage"
                      loading="lazy"
                      :src="`${kartclass.beginner}`"
                    />
                    </v-row>
                    <v-row>
                     <img
                     class="kcImage"
                      loading="lazy"
                      :src="`${kartclass.club}`"
                    />
                    </v-row>
                    <v-row>
                     <img
                      class="kcImage"
                      loading="lazy"
                      :src="`${kartclass.regional}`"
                    />
                    </v-row>
                    <v-row>
                     <img
                     class="kcImage"
                      loading="lazy"
                      :src="`${kartclass.state}`"
                    />
                    </v-row>
                    </div>
                 </v-card>
                  
              </v-col>
             
            </v-card>
              <v-card 
                    class="child2"
                   
                    
                     >
                  
                   
                        <v-card-text id="text" class="child2">
                            
                         {{kartclass.description}}
                       
                        <v-chip
                          id="chip"
                          class="child3"
                          color="#47539b"
                          v-for="t in kartclass.tech" :key="t"
                        >
                          {{t}}
                        </v-chip>
                      
                        </v-card-text>
                      <div v-for="link in kartclass.links" :key="link">
                        
                        <v-btn 
                          x-small 
                          class="mt-4 ml-12"
                          max-height="200px"
                          color="#0a75ad"
                         
                          >
                          {{link}}</v-btn>
                      
                      </div>
             
                </v-card>
                
          </v-col>
          
      </v-row>
      
</v-container>
</template>

<script>


export default { 

    props: ["kartclass"],

}
</script>

<style scoped>
#mainImg {
 
   max-height: 400px;
  max-width: 400;
  min-width: 100%;
  min-height: 250px;
  object-fit: contain;
}

.kcImage {
  max-height: 400px;
  max-width: 200px;
  min-width: 100%;
  min-height: 100px;
  object-fit:contain;
  margin-top: 2px;
}
#text {
    color:white;
    white-space: pre-line;
    position: relative;
    max-height: 400px;
    
}
#parent{
    display: flex;
    width: 1150px;
    height: 400px;
}
.child1{
 height: 400px;
 
}
.child2{
 height: 200px;
 display:inline-block;
   
}
.child3{
 height: 20px;
 justify-content: space-between;
}

#chip {
    padding: 15px;
    margin-left: 25px;
}
</style>