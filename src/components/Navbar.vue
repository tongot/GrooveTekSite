<template>
    <nav>
        <v-app-bar flat app  color="primary">
            <v-app-bar-nav-icon class="grey--text" @click="drawer=!drawer"></v-app-bar-nav-icon>
            <v-toolbar-title class="text-uppercase primary--text d-none d-lg-flex">
                <v-img src="@/assets/GrooveTekLogo.png">..</v-img>
            </v-toolbar-title>
            <v-spacer></v-spacer>
              <v-menu text color="black">
                 <template v-slot:activator="{on}">
                 <v-btn text color="black" class="d-flex d-sm-none" v-on="on" >
                     {{menu}}
                     <v-icon right>keyboard_arrow_down</v-icon>
                </v-btn>
                 </template>
                <v-list>
                    <v-list-item v-for="service in menuList" :key="service.menu" router :to="service.route" @click="menu=service.menu">
                        <v-list-item-content>
                            {{service.menu}}
                        </v-list-item-content>
                    </v-list-item>
                </v-list>
            </v-menu >
              <v-btn text color="black" class="d-none d-sm-flex" route to="/">
                <span>Home</span>
            </v-btn> 
             <v-btn text color="black" class="d-none d-sm-flex"  route to="/ourservices">
                <span>Services</span>
            </v-btn> 
             <v-btn text color="black" class="d-none d-sm-flex"  route to="/contactus">
                <span>Contact us</span>
            </v-btn>  
            <v-btn text color="black" class="d-none d-sm-flex"  route to="/about">
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
            menu:'home',
            links:[
                {icon:'dashboard',text:'Dashboard',route:'/'},
                {icon:'email',text:'Inbox',route:'/about'},
                {icon:'contact_support',text:'Contact Support',route:'/home'}
            ],
            menuList:[
                 {menu:'Home',route:'/'},
                {menu:'Services',route:'/ourservices'},
                {menu:'About',route:'/about'},
                {menu:'Contact Us',route:'/contactus'},
            ],
           
        }
    }
}
</script>