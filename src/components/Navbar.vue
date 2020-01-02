<template>
    <nav>
        <v-app-bar flat app  color="primary">
            <v-app-bar-nav-icon class="grey--text" @click="drawer=!drawer"></v-app-bar-nav-icon>
            <v-toolbar-title class="text-uppercase primary--text">
                <v-img src="@/assets/GrooveTekLogo.png">.</v-img>
            </v-toolbar-title>
            <v-spacer></v-spacer>
             <!-- <v-menu text color="black">
                 <template v-slot:activator="{on}">
                 <v-btn text color="black" v-on="on" >
                      Services
                </v-btn>
                 </template>
                <v-list>
                    <v-list-item v-for="service in services" :key="service.text" router :to="service.route">
                        <v-list-item-action>
                            <v-icon>{{service.icon}}</v-icon>
                        </v-list-item-action>
                        <v-list-item-content>
                            {{service.text}}
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
            </v-menu >-->
              <v-btn text color="black" route to="/">
                <span>Home</span>
            </v-btn> 
             <v-btn text color="black" route to="/ourservices">
                <span>Services</span>
            </v-btn> 
             <v-btn text color="black" route to="/contactus">
                <span>Contact us</span>
            </v-btn>  
            <v-btn text color="black" route to="/about">
                <span>About</span>
            </v-btn>            
            <!--<v-btn text color="black">
                <span>sign In</span>
                <v-icon right></v-icon>
            </v-btn>-->
        </v-app-bar>
        <!--<v-navigation-drawer app  v-model="drawer" color="primary">
           <v-list>
               <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
                   <v-list-item-action>
                       <v-icon class="white--text">{{link.icon}}</v-icon>
                   </v-list-item-action>
                   <v-list-item-content>
                       <v-list-item-title class="white--text">{{link.text}}</v-list-item-title>
                   </v-list-item-content>
               </v-list-item>
           </v-list>
        </v-navigation-drawer>-->
    </nav>
</template>
<script>
export default {
    data()
    {
        return{
            drawer:false,
            links:[
                {icon:'dashboard',text:'Dashboard',route:'/'},
                {icon:'email',text:'Inbox',route:'/about'},
                {icon:'contact_support',text:'Contact Support',route:'/home'}
            ],
            services:[
                 {icon:'business',text:'Services',route:'/ourservices'},
                {icon:'perm_data_setting',text:'Project Managment',route:'/about'},
                {icon:'developer_board',text:'Software Development',route:'/home'},
                {icon:'fiber_smart_record',text:'Electronic Records Management',route:'/home'},
                {icon:'cloud_circle',text:'Cloud Solution',route:'/home'},
                {icon:'phonelink',text:'Digital Marketing',route:'/home'},
               {icon:'wifi_lock',text:'IT Security',route:'/home'},
               {icon:'format_strikethrough',text:'ICT Infrastructure',route:'/home'},
            ],
           
        }
    }
}
</script>