<template>
<no-ssr>
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
              <v-col xs="12">
                  <v-img
                    max-width="750"
                    max-height="400"
                    height="auto"
                    width="100%"
                    :src="`${kartclass.image1}`"
                  />
                
              </v-col>
              <div class="d-flex align-start flex-wrap">
              <v-col  xs="12">
                 <v-card 
                    id="child1"
                     class="d-flex align-content-start"
                max-width="1244"
                    
                     >
                     
                     <div class="d-sm-none d-md-flex">
                        
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
                        
                    </div>
                 </v-card>
                  
              </v-col>
              </div>
            </v-card>
              <v-card>
                     
                <v-row class="d-flex justify-center pa-2">
                        <div v-for="link in kartclass.links" 
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
                            
                         {{kartclass.description}}
                    
                         <v-row class="d-flex justify-center mx-2 mb-2">
                        <v-chip
                          id="chip"
                          
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

    props: ["kartclass", "followLink"],
      methods:{
      followLink(link){
           console.log("link: " + link)
        switch (link) {
          case "Front-end Code":
              window.open("https://github.com/Jrad84/DS_Karting/", "_blank");
             
            break;
          case "Back-end Code":
              window.open("https://github.com/Jrad84/kartclass-backend/", "_blank");
              break;
          case "Demo":
              window.open("https://drive.google.com/file/d/1dRIsZJWDGZ-3z83TiQ9SWnekvjutmiqQ/view?usp=sharing", "_blank");
              break;
          default:
            break;
        }
      }
    }

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