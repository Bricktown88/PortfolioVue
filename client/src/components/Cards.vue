<template>
    <div>
  <v-layout row wrap>
      <v-flex xs12 sm6 md4 v-for="card in cards" :key="card.headline">
        <v-card hover height="400">
            <!-- <v-responsive :aspect-ratio="16/9"> -->
          <v-img :src="card.image" :aspect-ratio="16/9" :alt="card.alt">
          </v-img>
            <!-- </v-responsive> -->
  
          <v-card-title primary-title>
            <div>
              <h3 class="headline mb-0">{{ card.headline }}</h3>
              <div>{{card.description}}</div>
            </div>
          </v-card-title>
  
          <!-- <v-card-actions>
            <v-btn flat color="orange">Share</v-btn>
            <v-btn flat color="orange">Explore</v-btn>
          </v-card-actions> -->

<div class="text-xs-center">
      <v-dialog
        v-model="dialog"
        width="400"
      >
        <v-btn
          slot="activator"
          color="pink"
          dark
        >
          <span>Read More</span>
        </v-btn>
  
        <v-card>
          <v-card-title
            class="headline pink"
            primary-title
          >
            <span>{{card.headline}}</span>
          </v-card-title>
  
          <v-card-text>
              {{card.description}}
          </v-card-text>
  
          <v-divider></v-divider>
  
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn>
                <v-icon left>mdi-github-circle</v-icon>
                <span>GitHub</span>
            </v-btn>
            <v-btn
              color="red"
              flat
              @click="dialog = false"
            >
              <span>Close</span>
            <v-icon right>mdi-close-circle-outline</v-icon>
            </v-btn>
            
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>







        </v-card>
      </v-flex>
    </v-layout>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                dialog: false,
                cards: [
                    {
                        headline: 'Kangaroo', 
                        description: "Located two hours south of Sydney in the",
                        image: "https://cdn.vuetifyjs.com/images/cards/desert.jpg",
                        alt: "Kangaroo Image"
                    },
                    {
                        headline: 'Giphy API', 
                        description: "Click buttons to view GIFs, or add your own searchable button",
                        image: '../../static/giphy2.png',
                        alt: "Kangaroo2 Image2"
                    },
                    {
                        headline: 'Kangaroo3', 
                        description: "Located two hours south of Sydney in the",
                        image: "https://cdn.vuetifyjs.com/images/cards/desert.jpg",
                        alt: "Kangaroo Image3"
                    }
                ]
            }
        }
    }
</script>

<style scoped>

</style>