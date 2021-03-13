<template>
<v-container>
    <div class="col-xs-4 d-sm-block center-md">
        
      <v-row class="mt-12">
            
            <v-col
                  cols="12"
                  xs="1"
                  class="pa-4"
                  fluid="true"
            >
               <v-card
               id="parent"
                class="d-flex align-content-start"
                max-width="1244"
              >
             
              <v-col xs="1">
               
                    
                  <v-img
                    max-width="750"
                    max-height="400"
                    
                    :src="`${kartclass.image1}`"
                  />
               
              </v-col>
              <div class="d-flex align-start flex-wrap">
              <v-col  xs="1">
                 <v-card 
                    id="child1"
                    class="d-flex child-flex"
                    
                     >
                     
                     <div class="float-sm-left">
                         <v-row>
                            <v-img
                                class="mt-3 mr-2"
                                max-width="365"
                                max-height="360"
                                
                                :src="`${kartclass.image2}`"
                            />
                         </v-row>
                    </div>
                 </v-card>
                  
              </v-col>
              </div>
            </v-card>
              <v-card 
                   
                     >
                           <v-row class="ml-12" align="center">
                      <div v-for="link in kartclass.links" 
                      :key="link" 
                      justify-start
                      class="d-flex align-center flex-wrap"
                      >
                        
                        <v-col cols="12" xs="1">
                        <v-btn 
                          small 
                          class="mt-4 ml-12"
                          max-height="200px"
                          color="#0a75ad"
                          @click="followLink(link)"
                          >
                          {{link}}</v-btn>
                        </v-col>
                          
                      </div>
                      </v-row>
                  
                   <div  class="d-flex align-content-start">
                        <v-card-text id="text"  class="d-flex align-start flex-wrap">
                            
                         {{kartclass.description}}
                      
                        <v-chip
                          id="chip"
                          class="d-flex align-start flex-column"
                          color="#47539b"
                          v-for="t in kartclass.tech" :key="t"
                        >
                          {{t}}
                        </v-chip>
                      
                        </v-card-text>
                         </div>
                </v-card>
          </v-col>
          
      </v-row>
    </div>
</v-container>
</template>

<script>


export default { 
computed: {
      cols () {
        const { lg, sm } = this.$vuetify.breakpoint
        return lg ? [3, 9] : sm ? [9, 3] : [6, 6]
      },
    },
    props: ["kartclass", "followLink"],

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