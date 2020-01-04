<template>
    <div>
         <v-app-bar  height="35" dark>
      <v-toolbar-title>Contact Us</v-toolbar-title>
  </v-app-bar>
        <div>
        <v-img src="./homeImages/contact.jpg" height="500px" justify="center" align="center"></v-img>
        </div>
        <v-container>
            <v-row justify="space-around">
                <v-flex xs12 md4>
                    <h2 class="grey--text headline display-1">Just Get In Touch!</h2>
                    <v-divider></v-divider>
                    <p class="grey--text subtitle">We would love to hear from you</p>
                    <v-text-field v-model="name" :rules="nameRule" height="50px" label="Name"></v-text-field>
                    <v-text-field v-model="email" :rules="emailRule" height="50px" label="Email"></v-text-field>
                    <v-text-field v-model="subject"  height="50px" label="Subject"></v-text-field>
                    <v-textarea v-model="message" :counter=50 :rules="messageRule" label="Message"></v-textarea>
                    <v-row justify="end">
                        <v-btn class="primary" depressed><v-icon left>email</v-icon>Submit</v-btn>
                    </v-row>
                    
                </v-flex>
                <v-flex xs12 md4>
                     <h2 class="grey--text headline display-1">Our Addresses</h2>
                    <v-divider></v-divider>
                    <address>
                    <p class="grey--text subtitle">Plot 19709</p>
                    <p class="grey--text subtitle">Makatsomo Way Phase 2</p>
                    <p class="grey--text subtitle">Gaborone</p>
                       <p class="grey--text subtitle">Botswana</p>
                       <v-divider></v-divider>
                        <br><span class="white--black"><v-icon style="color:black">phone</v-icon>+267 310 1315</span>
                        <br><span class="white--black"><v-icon style="color:black">email</v-icon>support@groovetek.co.bw</span>
                    </address>
                </v-flex>
            </v-row>
        </v-container>
    </div>
</template>
<script>
export default {
    data:()=>({
                name:'',
                email:'',
                subject:'',
                message:'',
                nameRule:[
                    v=>!!v||"Name is required",
                    v=>v.length>=3||"Name must be at least 3 characters",
                ],
                emailRule:[
                     v=>!!v||"Email is required",
                     v=> /.+@./.test(v)||"Email must be a valid email"
                ],
                 messageRule:[
                    v=>!!v||"Message is required",
                    v=>v.length>=10||"Message must be at least 10 characters",
                    v=>v.length<=50||"Message must be less than 50 characters",
                ],
    })
}
</script>