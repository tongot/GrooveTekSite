<template>
  <div >
 <div class="pb-5">
   
    <v-carousel cycle height="500" hide-delimiter-background show-arrows-on-hover>
     
      <v-carousel-item v-for="product in products" :key="product.path">
        <v-sheet height="100%">
          <v-row class="fill-height" align="center" justify="center">
            <v-img :src="require(`./homeImages/${product.path}`)" class="fill-height" align="center" justify="center" >
             <v-row class="fill-height" align="center" justify="center">
               <div class="display-3 pa-4 black" style="opacity:0.5"><v-icon style="font-size:70px">{{product.icon}}</v-icon><span>{{product.text}}</span></div>
             </v-row>
            </v-img>
          </v-row>
        </v-sheet>
      </v-carousel-item>
      
    </v-carousel>
    <v-app-bar dark height="50px">
      <v-toolbar-title class="display-1">Our Products</v-toolbar-title>
      <v-spacer></v-spacer>
        <v-btn class="d-none d-lg-none d-xl-flex" text v-for="product in products" :key="product.path">
                <v-icon left>{{product.icon}}</v-icon>
                {{product.text}} |
            </v-btn> 
            <v-menu text color="black">
                 <template v-slot:activator="{on}">
                 <v-btn class="d-xl-none" text color="white" v-on="on" >
                      Products
                      <v-icon right>keyboard_arrow_down</v-icon>
                </v-btn>
                 </template>
                <v-list>
                    <v-list-item v-for="product in products" :key="product.text">
                        <v-list-item-action>
                            <v-icon>{{product.icon}}</v-icon>
                        </v-list-item-action>
                        <v-list-item-content>
                            {{product.text}}
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
            </v-menu >
    </v-app-bar>
  </div>

 <v-container>
      <v-row class="mb-5">
        <v-flex class=" pa-5" xs8 md3>
          <h1 class="orange--text display-2 font-weight-bold">Our Company</h1>
        </v-flex>
        <v-flex xs4 md9>

        </v-flex>
      </v-row>
      <v-row  class="mb-5">
        <v-flex xs12 md4 class="black pa-4"> 
            <p class="white--text headline font-weight-light"><span class="white--text display-4 font-weight-bold">"</span>We are young, energetic, curious and committed minds, excited about solving complex business problems”</p>
        </v-flex>
        <v-flex xs12 md8>
            <p class="subtitle-1 ma-4">Groove Tek is a young company In Gaborone, Botswana’s capital city. We say we’re young because we’re peopled by young, energetic, curious and committed minds who are excited about solving complex business problems, ethically. Conceived with a vision to leave behind a legacy of transformed peoples as an organization, we place a high emphasis on working in partnership with customers.</p>
            <p class="subtitle-1 ma-4">Our experience has taught us that to provide any solutions; we need creativity and lots of inspired thinking, our experienced professionals along with the 'let-us-do-it' attitude of the fresh talent is constantly pushing the horizons Our values of Integrity, Service, Candor, Kindness, Growth and Continually Increasing Competence govern our behavior towards all our stakeholders.</p>
        </v-flex>
      </v-row>
      <v-row class="mb-5">
        <v-flex class=" pa-5" xs8 md3>
          <h1 class="orange--text display-2 font-weight-bold">Partners</h1>
        </v-flex>
        <v-flex xs4 md9>

        </v-flex>
      </v-row>
      <v-row no-gutters>
      <v-col
        cols="12"
        md="4"
        v-for="image in images" :key="image.text"
        align="center"
      >
        <v-card flat max-width="500px" justify="center" class="mx-10" >
            <v-img :height="imageH(image.path)" :width="imageW(image.path)" :src="require(`./homeImages/${image.path}`)"></v-img>
            <p class="headline text-md-center grey--text">{{image.text}}</p>
        </v-card>
      </v-col> 
    </v-row>
    </v-container>

<!--partners section-->
    
  </div>
</template>

<script>

export default {
 data: () => ({
         images:[
           {path:'microLogo.png',headText:'Microsoft',text:'Cloud Solution Provider'},
           {path:'microLogo.png',headText:'Microsoft',text:'Silver Partner'},
           {path:'Micro-Focus.png',headText:'MicroFocus',text:'Gold Partner'},
         ],
         certifications:[
            {path:'itil.png'},
           {path:'microsoftCertifications.png'},
           {path:'networksAndHacking.png'},
         ],
        products:[
           {path:'insurancemng.jpg',text:'Insurance Managment System', icon:'supervisor_account'},
           {path:'human2.jpg' ,text:'Human Resource Management System', icon:'people'},
           {path:'travel2.jpg' ,text:'Travel management system', icon:'flight_takeoff'},
           {path:'loans.jpg',text:'Quick Loans', icon:'attach_money'},
           {path:'patient2.jpg' ,text:'Botsogo Patient Management', icon:'pregnant_woman'},
        ]
              
  }),
  methods:{
    imageH(name){
       if(name=='Micro-Focus.png'){
         return '73px';
       }
       return '70px'
    },
    imageW(name){
        if(name=='Micro-Focus.png'){
         return '178px';
       }
       return '70px'
    }
  }
}
</script>
