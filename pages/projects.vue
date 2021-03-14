<template>
  <div >
    <Kartclass :kartclass="kartclass" :followLink="followLink" />
    <CV :item="cv" />
 
  </div>
</template>

<script>
import Image1 from "~/assets/kc1.png"
import Image2 from "~/assets/mask_256_40.png"
import Image3 from "~/assets/spaceX.jpg"
import Image4 from "~/assets/kc2.png"
import Mask from "~/assets/mask.png"
import Kartclass from "~/components/Kartclass"
import CV from "~/components/CV"
const data = {
              title: "KartClass",
              image1: Image1,
              image2: Image4,
              description: "KartClass is a website I was commissioned to build by 18x Australian Go Karting champion, David Sera. " +
                  "The goal of Kartclass is to provide the next generation of motor sports enthusiasts with the knowledge that" + 
                 "is normally reserved for a small minority, helping to level the playing field." + "\n\n" + 
                 "Stripe payment platform has been integrated to handle payments & Python handles all of the business logic on the backend. " +
                 "It also features an Admin page with standard CRUD operations and a dashboard displays various user and content metrics calculated via " +
                 "Vue JS computed properties." 
                ,
              tech: [
                "Python",
                "Nuxt js",
                "Django REST Framework",
                "Stripe",
                "PostgreSQL"
               ],
               links: [
                 "Front-end code",
                 "Back-end code",
                 "View site"
               ]
        }
const cvData = {
    
                    title: "Computer Vision project",
                    image1: Image2,
                    image2: Mask,
                    subtitle: "Final year CS Project",
                    description: "My final year CS project involved developing a computer vision system that could " +
                    "recognize various components placed on a board and convert the board configuration into a graph of " +
                    "connected nodes and edges which would be used to determine the validity of the users configuration. " +
                    "My role in this project was Team Leader and I was responsible for keeping the team happy, motivated "+
                    "and on track as well as presenting our updates weekly to our client. My key contribution to the " +
                    "project was finding & implementing Mask-RCNN - a segmentation model that was the key to solving the " +
                    "problem.",
                    tech: [
                      "Python",
                      "TensorFlow",
                      "OpenCV"
                    ],
                    links: [
                      "Demo"
                    ]
               
}
export default {
  head() {
    return {
      title: "Projects"
    };
  },
    asyncData(context) {
    let kc = data;
    let c = cvData;
    return {
      kartclass: kc,
      cv : c
    };
  },
    data(){
        return {
          kartclass: {},
          cv: {}
              
           }
    },
        
            //      {
            //         title: "SpaceX Mobile app",
            //         image: Image3,
                   
            //         description: "For my custom project in my mobile app develeopment class, I developed an app to track both upcoming and past SpaceX launches including details about the launch and details about the different rockets used.",
            //         tech: [
            //           "Java",
            //           "GraphQL"
                     
            //         ],
            //         links: [
            //           "Code"
            //         ]
            //     }
            // ]
        
    
    components:{
      Image1,
      Image2,
      Image3,
      Image4,
     Mask,
      CV
    },
    methods:{
      followLink(link){
        switch (link) {
          case "Front-end Code":
              window.open("https://github.com/Jrad84/DS_Karting/", "_blank")
              console.log("link: " + link)
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