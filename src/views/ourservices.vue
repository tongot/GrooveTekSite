<template>
<div>
  <v-app-bar  height="35" dark>
      <v-toolbar-title>Our Services</v-toolbar-title>
  </v-app-bar>
<v-container>
  <v-sheet elevation="2">
            <div >
                 <v-card outlined class="pa-2">
                <v-row >
                    <v-flex sm12 md6>
                        <v-img src="../views/homeImages/human2.jpg"></v-img>
                    </v-flex>
                     <v-flex sm12 md6  class="pa-5 justify-center align-center">
                        <h1 class=" display-1">Our services</h1>
                        <p class="font-weight-medium subtitle-1">Groove Tek delivers quality and timely solutions and services at a price that make our clients smile. An in-depth knowledge of various technology areas enables us to provide end to-end solutions and services. With our 'Web of Participation', we maximize the benefits of our depth, diversity and delivery capability, ensuring adaptability to client needs, and thus bringing out the most innovative solutions in every business and technology domain.
                            </p><p class="font-weight-medium subtitle-1">Groove Tek is your one stop partner where you can outsource all your IT services with complete peace of mind about quality and reliability. Our Software Solution’s strength lies in understanding the client’s business processes, culture, vision and goals across the industry segments and offering client oriented solutions which are highly reliable, creating customer comfort. 
                            Our team is committed to provide IT Services with:  Quality | Technology | Innovation
                        </p>
                    </v-flex>
                </v-row>
                <v-row justify="center" align="center">
                  <v-card-actions>
                    <v-btn class="d-none d-lg-none d-xl-flex" text @click="component=service.route;" v-for="service in services" :key="service.text">
                      <v-icon left>{{service.icon}}</v-icon>
                      {{service.text}}
                    </v-btn>
                    <v-menu text color="black" class="d-xl-none">
                 <template v-slot:activator="{on}">
                 <v-btn class="d-xl-none" text color="black" v-on="on" >
                      Services
                      <v-icon right>keyboard_arrow_down</v-icon>
                </v-btn>
                 </template>
                <v-list>
                    <v-list-item @click="component=service.route" v-for="service in services" :key="service.text">
                        <v-list-item-action>
                            <v-icon>{{service.icon}}</v-icon>
                        </v-list-item-action>
                        <v-list-item-content>
                            {{service.text}}
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
            </v-menu >
                  </v-card-actions>
                </v-row>
                </v-card>
                
                 <div>
                   <transition>
                        <compontent v-bind:is="component"></compontent>
                   </transition>
                 </div>
            </div></v-sheet>
            </v-container>
            </div>
</template>
<script>

import businessAnalysis from '@/components/businessAnalysis.vue'
import projectManagment from '@/components/projectManagment.vue'
import softwareDev from '@/components/softwareDev.vue'
import electronic from '@/components/Electronic.vue'
import cloudSolution from '@/components/cloudSolution.vue'
import digitalMarketing from '@/components/digitalMarketing.vue'
import Infrastructure from '@/components/infrastructure.vue'
import ItSecurity from '@/components/ItSecurity.vue'



export default {
  name: 'App',
  components:{
     'businessAnalysis':businessAnalysis,
     'projectManagment':projectManagment,
     'softwareDev':softwareDev,
     'electronic':electronic,
     'cloudSolution':cloudSolution,
     'digitalMarketing':digitalMarketing,
     'Infrastructure':Infrastructure,
     'ItSecurity':ItSecurity
    },
  data: () => ({
    component:'businessAnalysis',
    services:[
                 {icon:'business',text:'Business Analysis',route:'businessAnalysis'},
                {icon:'perm_data_setting',text:'Project Mgmt',route:'projectManagment'},
                {icon:'developer_board',text:'Software Development',route:'softwareDev'},
                {icon:'fiber_smart_record',text:'Electronic Records Mgmt',route:'electronic'},
                {icon:'cloud_circle',text:'Cloud Solution',route:'cloudSolution'},
                {icon:'phonelink',text:'Digital Marketing',route:'digitalMarketing'},
               {icon:'wifi_lock',text:'IT Security',route:'ItSecurity'},
               {icon:'format_strikethrough',text:'ICT Infrastructure',route:'Infrastructure'},
            ],

  }),
};
</script>
<style scoped>
  .v-enter-active{
    animation: bounceIn 2s;
  }
  @keyframes bounceIn{
    0%{
      transform: scale(0.1);
      opacity: 0;
    }
     
    100%{
      transform: scale(1);
      opacity: 1;
    }
  }

</style>