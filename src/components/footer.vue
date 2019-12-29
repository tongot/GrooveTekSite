<template>
    <div>
        <v-row>
            <v-flex md3 xs6 class="primary">
                 <v-list class="primary ml-10">
                    <v-list-item v-for="service in services1" :key="service.text">
                        <v-list-item-action>
                            <v-icon style="font-size:30px; color:white;"  >{{service.icon}}</v-icon>
                        </v-list-item-action>
                        <v-list-item-content>
                            <span class="font-weight-normal white--text">{{service.text}}</span>
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
            </v-flex>
            <v-flex md3 xs6 class="primary">
            <v-list class="primary">
                    <v-list-item v-for="service in services2" :key="service.text">
                        <v-list-item-action>
                            <v-icon style="font-size:30px; color:white;"  >{{service.icon}}</v-icon>
                        </v-list-item-action>
                        <v-list-item-content>
                            <span class="font-weight-normal white--text">{{service.text}}</span>
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
            </v-flex>
            <v-flex md3 xs6 class="primary">
            <v-list class="primary">
                    <v-list-item v-for="service in services3" :key="service.text" route :to="service.route">
                        <v-list-item-action>
                            <v-icon style="font-size:30px; color:white;"  >{{service.icon}}</v-icon>
                        </v-list-item-action>
                        <v-list-item-content>
                            <span class="font-weight-normal white--text">{{service.text}}</span>
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
            </v-flex>
            <v-flex md3 xs6 class="d-flex align-end justify-end pa-5 black">
                <address >
                    <br><span class="white--text"><v-icon style="color:white">phone</v-icon>+267 310 1315</span>
                    <br><span class="white--text"><v-icon style="color:white">email</v-icon>support@groovetek.co.bw</span>
                </address>
            </v-flex>
        </v-row>
        <v-row class="grey darken-4">
            <v-flex md4>
                <span class="ml-10 subtitle-2 white--text font-weight-thin"><i>Powered By GrooveTek &copy;{{getyear()}}</i></span>
            </v-flex>
            <v-flex md4>
                
            </v-flex>
            <v-flex md4>
               
            </v-flex>
        </v-row>
    </div>
</template>
<script>
export default {
    data:()=>({
         today:null,
         services1:[
                 {icon:'business',text:'Services',route:'/ourservices'},
                {icon:'perm_data_setting',text:'Project Managment',route:'/about'},
                {icon:'developer_board',text:'Software Development',route:'/home'},
                {icon:'fiber_smart_record',text:'Electronic Records Management',route:'/home'},
            ],
        services2:[
             {icon:'cloud_circle',text:'Cloud Solution',route:'/home'},
                {icon:'phonelink',text:'Digital Marketing',route:'/home'},
               {icon:'wifi_lock',text:'IT Security',route:'/home'},
               {icon:'format_strikethrough',text:'ICT Infrastructure',route:'/home'},
        ],
        services3:[
             {icon:'filter_1',text:'Home',route:'/'},
                {icon:'filter_2',text:'Vision, Mission, Values',route:'/about'},
               {icon:'filter_3',text:'Our Services',route:'/ourservices'},
               {icon:'filter_4',text:'Our Contacts',route:'/home'},
        ]
    }),
    methods:{
        getyear(){
            this.today= new Date();
            return this.today.getFullYear();
        }
    }
}
</script>