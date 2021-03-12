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
                          @click="followLink(link)"
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
import Image3 from "~/assets/spaceX.jpg"
export default {
    data(){
        return{
           
            items: [
                {
                    title: "KartClass",
                    image: Image1,
                    subtitle: "Subscription based Coaching web app",
                    description: "KartClass is a website I was commissioned to build by 18x Australian Go Karting champion, David Sera. It integrates Stripe payments platform & Python handles all of the business logic on the backend. It also features an Admin page with standard CRUD options and various user and content metrics calculated via Vue JS computed properties.",
                    tech: [
                      "Python",
                      "Nuxt js",
                      "Django REST Framework",
                      "PostgreSQL"
                    ],
                    links: [
                      "Front-end Code",
                      "Back-end Code"
                    ]
                },
                {
                    title: "Computer Vision project",
                    image: Image2,
                    subtitle: "Final year CS Project",
                    description: "My final year CS project involved developing a computer vision system that could recognize various components placed on a board and convert the board configuration into a graph of connected nodes and edges which would be used to determine the validity of the users configuration. My role in this project was Team Leader and I was responsible for keeping the team happy, motivated and on track as well as presenting our updates weekly to our client. My key contribution to the project was finding & implementing Mask-RCNN - a segmentation model that was the key to solving the problem.",
                    tech: [
                      "Python",
                      "TensorFlow",
                      "OpenCV"
                    ],
                    links: [
                      "Demo"
                    ]
                },
                 {
                    title: "SpaceX Mobile app",
                    image: Image3,
                   
                    description: "For my custom project in my mobile app develeopment class, I developed an app to track both upcoming and past SpaceX launches including details about the launch and details about the different rockets used.",
                    tech: [
                      "Java",
                      "GraphQL"
                     
                    ],
                    links: [
                      "Code"
                    ]
                }
            ]
        }
    },
    components:{
      Image1,
      Image2,
      Image3
    },
    methods:{
      followLink(link){
        switch (link) {
          case "Front-end Code":
              window.open("https://github.com/Jrad84/DS_Karting/", "_blank")
            
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
/* .card2 {
  color:#0a75ad
} */

img {
 
   max-height: 275px;
  max-width: none;
  min-width: 100%;
  min-height: 250px;
}
</style>