<template>
  
     
  <v-container>
        <v-row>
            <v-col cols="6" md="3" class="pa-8 mt-12">
                <v-card
                    class="mx-auto"
                    max-width="344"
                    id="card1"
                >
                    <v-card-text>
                    <div >Study</div>
                    <p class="text--primary">
                        BSc Computer Science
                    </p>
                    <div>Major</div>
                  
                     <p class="text--primary">   Software Development</p>
                      <div>School</div>
                  
                     <p class="text--primary">Swinburne University of Technology</p>
                  
                    </v-card-text>
                    <v-card-actions>
                    <v-btn
                        text
                        color="teal accent-4"
                        @click="reveal = true"
                    >
                        Learn More
                    </v-btn>
                    </v-card-actions>

                    <v-expand-transition>
                    <v-card
                        v-if="reveal"
                        class="transition-fast-in-fast-out v-card--reveal"
                        style="height: 100%;"
                    >
                        <v-card-text class="pb-0">
                        <p class="display-1 text--primary">
                            
                        </p>
                        <p>I decided on a career change after completing a few online coding courses and it turned
                          out to be the best decision for me as I felt like I had finally discovered something I was
                          passionate about. I love creating applications from code and all of the joys and frustrations involved,
                          especially solving a problem that's had me stuck for days!
                           </p>
                        </v-card-text>
                        <v-card-actions class="pt-0">
                        <v-btn
                            text
                            color="teal accent-4"
                            @click="reveal = false"
                        >
                            Close
                        </v-btn>
                        </v-card-actions>
                    </v-card>
                    </v-expand-transition>
                </v-card>
            </v-col>
        </v-row>
      
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      reveal: false,
    }),
  }
</script>
<style>
#myVideo {
  object-fit: cover;
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
}
.v-card--reveal {
  bottom: 0;
  opacity: 1 !important;
  position: absolute;
  width: 100%;
}
#card1 {
    position: relative;
    z-index: 1
}
</style>