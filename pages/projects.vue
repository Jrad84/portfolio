<template>
  <div>

 <v-container>
      <v-row class="mt-12">
            
            <v-col
                  v-for="(item, i) in items"
                  :key="i"
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
                      height="300px"
                      :src="`${item.image}`"
                  />
               </div>
              </v-col>
              <v-col>
                 <v-card class="mr-1" color="#0a75ad" >
                    <v-card-title>
                        {{item.title}} -
                         <v-card-subtitle>
                           {{item.subtitle}}
                         </v-card-subtitle>
                    </v-card-title>
                  
         

                        <v-card-text>
                          {{item.description}}
                        </v-card-text>
                        <v-row>
                      <div justify-content-center v-for="link in item.links" :key="link">
                        
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
  </div>
</template>

<script>
import Image1 from "~/assets/kc1.png"
import Image2 from "~/assets/mask_256_40.png"
export default {
    data(){
        return{
           show: false,
            items: [
                {
                    title: "KartClass",
                    image: Image1,
                    subtitle: "Subscription based Coaching web app",
                    description: "KartClass is a website I was commissioned to build by 18x Australian Go Karting champion, David Sera. It integrates Stripe payments platform and data is served from the backend API built using Django REST Framework. It also features an Admin page with standard CRUD options and various user and content metrics calculated via Vue JS computed properties.",
                    tech: [
                      "Python",
                      "Nuxt js",
                      "Django REST Framework",
                      "PostgreSQL"
                    ],
                    links: [
                      "Data Schema",
                      "Front-end Code",
                      "Back-end Code"
                    ]
                },
                {
                    title: "Computer Vision project",
                    image: Image2,
                    subtitle: "Final year CS Project",
                    description: "",
                    tech: [
                      "Python",
                      "TensorFlow",
                      "OpenCV"
                    ],
                    color: "transparent"
                }
            ]
        }
    },
    components:{
      Image1,
      Image2
    }
}
</script>
<style scoped>
/* .card2 {
  color:#0a75ad
} */

img {
 
  object-fit: cover;
}
</style>