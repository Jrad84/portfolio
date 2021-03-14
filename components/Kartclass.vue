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
                          @click="followLink(link)"
                          >
                          {{link}}</v-btn>
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
/* #mainImg {
 
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
} */
</style>