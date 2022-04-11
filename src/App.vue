<template>
  <div>



          <!-- Navigation bar starts here -->
          <div class="container pr-0" v-if="navbarShowing">
            <div class='dashboard'>
              <div class="sidebar">
                <nav class="navbar navbar-expand-lg navbar-light bg-white">
                  <div class="container-fluid">
                    <div  class="img-fluid">
                      <img v-on:click="clickHome"   class="img-fluid" src="./assets/images2/smartTherapy.png" alt="Active Module">
                    </div>
                    <div class="collapse navbar-collapse" id="navbarSupportedContent">
                      <!-- <button v-on:click="clickLogin" type="button" class="btn btn-outline-primary ">Login</button>
                      <button v-on:click="clickRegister" type="button" class="btn btn-outline-secondary">Register</button> -->
                    </div>
                  </div>
                </nav>
              </div>
            </div>
          </div>
        <!-- Navigation bar ends here -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->






      <!-- Sidebar Starts here -->
      <div v-if="sidebarShowing">
        <div class="sidebar2">
          <!-- <div class="logo">
          </div> -->
          <div class="navbar2 text-start">
            <h3 class="mb-5 text-start">
              <small class="text-muted "></small>
            </h3>
            <ul>
              <li class='active'>
                <div class="card mb-5">
                      <div class="card-body">
                          <h6 class="card-title px-2 py-2 text-start">Smart Performing Partner</h6>
                          <p class="card-text px-2 py-2 text-muted text-start">This application is AI powered therapy assisstant</p>
                          <div class="text-end px-2 py-2">
                              <a href="#" class="btn btn-light px-2 py-2"></a>
                          </div>
                      </div>
                  </div>
              </li>
              <li class="navbar2-item">
                <a class="navbar2-support">
                <em class="icon-headphones"></em>
                </a>
                <div @click="logOut()" class="signOut"></div>
              </li>
            </ul>
          </div>
        </div>
      </div>
        <!-- Sidebar ends here -->
              <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->







      <!-- Article list start here -->
              <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <div v-if="listArticleShowing">
    
          <div v-if="isNameCorrect">

            <div class="container pr-0 " >
              <div class='dashboard'>
                <div class="dashboard-content wow fadeIn" data-wow-delay="1s">
                  <h3 class="mb-5 text-start">
                    <small class="text-muted ">Start the chat</small>
                  </h3>
                  <div >
                    
                    <div class="learn-object-preview" v-for="(que,k) in questions" :key="k">
                      <div class="learn-object-info" >
                        <div class="row">
                          <div class="col-10">
                            
                            <div class="container22 lighter21">
                              <span class="spanleft">{{name1}}:</span>
                              <h6 >{{questions[k][0]}}</h6>
                            </div>
                          </div>
                        </div>
                      </div>
                      <div class="learn-object-info" >
                        <div class="row">
                          <div class="col-10">
                            
                            <div class="container22 lighter22">
                              <span class="spanleft">Machine:</span>
                              <h6 >{{questions[k][1]}}</h6>
                            </div>
                          </div>
                        </div>  
                      </div>
                        
                        
                    </div>
                    <div class="learn-object-info" >
                          <div class="row" >
                            <div class="col-10">
                              <div class="container4 lighter_message">

                                <div class="mb-3">
                                  <label for="exampleFormControlTextarea1" class="form-label">Enter your message:</label>
                                  <textarea v-model="message" placeholder="add multiple lines" class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
                                </div>
                                <div class="learn-object-send">
                                  <button
                                  class="btn primary ml-auto"
                                  @click="nextQuestion(message)"
                                >Send</button>
                            </div>
                              </div>
                            </div>
                          </div>
                        </div>
                    
                  </div>

                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- Article list ends here -->
              <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->






        <!-- Article text starts here -->
              <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->

        <div class="container pr-0 " v-if="textArticleShowing">
          <div class='dashboard'>
            <div class="dashboard-content wow fadeIn" data-wow-delay="1s">
              <div class="card mb-5">
                    <div class="card-body">
                        <h5 class="card-title px-2 py-2 text-start">Meta Verse</h5>
                        <p class="card-text px-2 py-2 text-muted text-start">The content of meta verse comes here</p>

                    </div>
                </div>
            <div class="text-end px-2 py-2">
              <a href="#" v-on:click="getArticleList" class="btn btn-light px-2 py-2">Back to All Articles</a>
            </div>
          </div>
        </div>
      </div>


      <!-- Article text ends here -->
              <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->




      <!-- Login starts here -->
              <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <div v-if="loginShowing">
          
          <h1>Login Page</h1>
          
        </div>

        <!-- Login ends here -->
              <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
        <!-- &&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&& -->
      <div v-if="!isNameCorrect">
        <modal class="container22" name="submitShow" height="auto" :width="350" :scrollable="true">
          <div class="modal-content modal-delete-content">
            <div class="modal-body modal-delete-body">
              Talk with an AI Therapist
            </div>
            <br>
            <input v-model="name1" placeholder="Your Name:">
            <div class="modal-footer justify-content-center">
            <!-- <button
                type="button"
                @click="$modal.hide('submitShow');"
                class="btn medium default"
              >No</button> -->
              <button
                type="button"
                @click="getName"
                class="btn medium primary"
              >Submit</button>
            </div>
          </div>
      </modal>
    </div>




  <router-view/>
  </div>
</template>



<script>
import axios from 'axios';
export default {
  watch: {
            titlePage: {
                immediate: true,
                handler() {
                    document.title = this.titlePage;
                }
            }
        },
  data() {
        return {
          navbarShowing: true,
          sidebarShowing: true,
          listArticleShowing: true,
          textArticleShowing: false,
          loginShowing: false,
          titlePage: 'Smart Performing Partner - Dashboard',
          message: "",
          respond:"",
          testChat:[],
          questions:[],
          name1:"",
          isNameCorrect: false,
          totalMessages:""
        }
    },
    async created() {
      this.alertShow()


    },
  methods: {
    getName(){
      if (this.name1 != ""){
        this.isNameCorrect = true
        this.$modal.hide('submitShow')
      }
      else{
        this.alertShow()
      }
    },
    alertShow() {
         this.$modal.show('submitShow');
        },
    nextQuestion(message){
      let temp_message = []
      temp_message.push("I am not shy. I say exactly what I think and I’m rewarded for it. Like one time, I had nothing to lose so I stood up in front of thousands of people and there were jokes that I told. They were so funny but I can’t hear laughter. But there was laughter and it was great, and it was because I was not shy. I know that each day will be great and I will enjoy each day with a fresh cup of coffee from Starbucks at 1400 E. Carson St., Pittsburgh, PA 15203 Closes 8 PM.")
      temp_message.push("Talking is important for generating a feeling of comradery. This is why I enjoy watching a ball game with friends, like England versus New Zealand – Test Match – Day1, Lord’s, London, United Kingdom. Venue Capacity 30000. This is how we like to feel. These are the kind of times we like to enjoy over a fantastic salad with sliced pears.")
      temp_message.push("Diets can be a troubling topic to negotiate in the context of career pressures, body image issues, and self-soothing. I feel great because I have the energy to work hard and enjoy the things I love to do. I love working on cytochrome-C proteins derived from large mammals, including elephants, who have large ears and very good hearing. They are sensitive animals. Artificial intelligence can make a fine companion, including physical intimacy. Smartdollworld.com. Blade Runner 1982.")
      this.totalMessages = ""
      // if ((this.questions.length)!=0){
      //   this.totalMessages = this.questions[0][0]+'\n'
      //   this.totalMessages = this.totalMessages + 'Nick: '+this.questions[0][1]+'\n'
      //   for (let i =1; i<(this.questions.length);i++)
      //   {
      //     this.totalMessages = this.totalMessages + 'Emily: '+this.questions[i][0]+'\n'
      //     this.totalMessages = this.totalMessages + 'Nick: '+this.questions[i][1]+'\n'
      //   }
      //   this.totalMessages = this.totalMessages + 'Nick: '+message
      // }
      // else{
      //   this.totalMessages = message
      // }
      this.totalMessages = message
      let answer = this.totalMessages
      const fb = new FormData();
      fb.append("text", answer);
      fb.append("name", this.name1)
      
      axios.post('https://chat-text-2.herokuapp.com/', fb)
      .then(response =>{this.temp1 = [],
        this.temp1.push(message),
        this.temp1.push(response.data.answer),
        this.questions.push(this.temp1)
        
      })
    },
    readArticle(id) {
      this.listshowing = false
      console.log(id)

    },
    listArticle() {
      this.listshowing = true

    },
    getArticleList(){
      this.navbarShowing= true,
      this.sidebarShowing= true,
      this.listArticleShowing= true,
      this.textArticleShowing= false,
      this.loginShowing= false,
      this.titlePage= 'Smart Performing Partner - Article'
    },
    getArticle(){
      this.navbarShowing= true,
      this.sidebarShowing= true,
      this.listArticleShowing= false,
      this.textArticleShowing= true,
      this.loginShowing= false,
      this.titlePage= 'Smart Performing Partner - Article'
    },
    clickLogin(){
      this.navbarShowing= true,
      this.sidebarShowing= false,
      this.listArticleShowing= false,
      this.textArticleShowing= false,
      this.loginShowing= true,
      this.titlePage= 'Smart Performing Partner - Login'
      axios.get(`http://localhost:3000/users/1`)
      .then(response => {
        // JSON responses are automatically parsed.
        let posts = response.data
        console.log(posts)
        console.log("OK")
      })
      .catch(e => {
        console.log(e)
      })
    },
    clickHome(){
      this.navbarShowing= true,
      this.sidebarShowing= true,
      this.listArticleShowing= true,
      this.textArticleShowing= false,
      this.loginShowing= false,
      this.titlePage= 'Smart Performing Partner - Dashboard'
    },
    created() {
      this.navbarShowing= true,
      this.sidebarShowing= true,
      this.listArticleShowing= true,
      this.textArticleShowing= false,
      this.loginShowing= false,
      this.titlePage= 'Smart Performing Partner - Dashboard'

      
    }
  }
}


</script>






<style lang="scss">
@import "./styles/variables.scss";
@import "./styles/mixin.scss";
@import "./styles/base.scss";
@import "./styles/learning.scss";
@import "./styles/modal.scss";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.sidebar2 {
  .signOut {
    color: $input-error-color;
    @include font-regular;
    cursor: pointer;
    text-decoration: underline;
    @include media-breakpoint(sm) {
      margin: 0 0 0 10px;
    }
    @include media-breakpoint(md) {
      @include position(fixed, null, null, 30px, 20px);
    }
    @include media-breakpoint(xl) {
      @include position(null, null, null, 30px, 50px);
    }
  }
  @include position(fixed, 0, 0, 0, 0);
  width: 100%;
  z-index: 200;
  @include flexProperty(space-between, null, column);
  padding: 20px;
  background-color: $white;
  max-height: 100%;
  overflow: auto;
  @include media-breakpoint(sm) {
    @include flexProperty(flex-start, null, row, wrap);
    max-height: inherit;
    bottom: auto;
  }
  @include media-breakpoint(md) {
    width: 180px;
  }
  @include media-breakpoint(xl) {
    width: 230px;
    padding: 50px 10px 0 50px;
  }
  .logo {
    width: 160px;
    @include media-breakpoint(sm) {
      width: 48px;
      overflow: hidden;
      flex: none;
    }
    a {
      display: block;
      flex: none;
      img {
        @include media-breakpoint(sm) {
          width: 170px;
          flex: none;
          max-width: inherit;
        }
      }
    }
  }
  .navbar2 {
    @include font-bold;
    margin: auto 0;
    padding: 0;
    font-size: 14px;
    @include media-breakpoint(sm) {
      width: 100%;
      font-size: 16px;
    }
    ul {
      margin: 0;
      list-style: none;
      @include media-breakpoint(sm) {
        @include flexProperty;
        width: 100%;
      }
    }
    li {
      margin: 30px 0 0;
      @include media-breakpoint(sm) {
        padding: 0 45px 0 0;
        margin: 20px 0 0;
        span {
          display: none;
        }
      }
      &.navbar-item {
        margin: 50px 0 0;
        @include media-breakpoint(sm) {
          @include position(fixed, 0, 0);
          @include flexProperty(null, center);
          margin: 0;
          padding: 20px;
          width: auto;
        }
      }
    }
    a {
      color: $list-color;
      cursor: pointer;
      &:hover {
        color: $black;
      }
    }
    .navbar-support {
      @include font-semiBold;
      font-size: 15px;
      border-radius: 5px;
      display: inline-block;
      border: solid 1px $primary-button-color;
      background-color: $light-button-color;
      padding: 6px 14px;
      color: $primary-button-color;
      em {
        margin: 3px 5px 0 0;
        font-size: 12px;
      }
      &:hover {
        color: $primary-button-color;
      }
    }
    .active {
      a {
        color: $primary-button-color;
      }
    }
  }
  .footer {
    padding: 20px 0 60px;
    @include media-breakpoint(sm) {
      @include flexProperty(null, flex-end);
      @include position(fixed, null, null, 0, 0);
      padding: 10px 10px 20px 20px;
      background: $white;
      width: 100%;
      height: 76px;
      box-shadow: rgba(0,0,0,0.07) 0 0 20px;
    }
    .footer-image {
      width: 39px;
      height: 39px;
      overflow: hidden;
      flex: none;
      border-radius: 100%;
      background: url('./assets/images/SimplifiedMetaverse_logo.png') no-repeat;
      background-position: center;
      background-size: contain;
      img {
        @include imageSize;
      }
    }
    .footer-content {
      @include media-breakpoint(sm) {
        flex: 1;
        margin: 0 0 0 15px;
        text-overflow: ellipsis;
        overflow: hidden;
        white-space: nowrap;
      }
    }
    .footer-title {
      @include font-black;
      font-size: 20px;
      margin: 8px 0 0;
      @include media-breakpoint(sm) {
        margin: 0;
        text-overflow: ellipsis;
        overflow: hidden;
      }
    }
    .footer-subtitle {
      @include font-medium;
      font-size: 14px;
      line-height: 1.21;
      color: $list-color;
      @include media-breakpoint(sm) {
        text-overflow: ellipsis;
        overflow: hidden;
      }
    }
  }
}
.spanleft{
  float: left;
}
.container23 {

    background-color: #f1f1f1;
    border: 1px solid #dedede;
    float: left;
    border-radius: 15px;
    padding: 10px;
    margin: 10px;

  }
.container22 {

    background-color: #f1f1f1;
    border: 1px solid #dedede;
    float: right;
    border-radius: 15px;
    padding: 10px;
    margin: 10px;

  }
  .lighter21 {
    float: left;
    border-color: rgb(35, 153, 133);
    background-color: rgb(35, 153, 133);
    color: white;
  }
  .lighter22 {
    float: right;
    border-color: rgb(35, 100, 153);
    background-color: rgb(35, 100, 153);
    color: white;
  }

  .modal-delete {
    .modal-delete-content {
        padding: 30px;
        min-height: 180px;
        color: #212121;
    }
    .btn {
        padding: 10px 15px;
        min-width: 100px;
    }
    .default {
        border: 0;
        color: #848484;
    }
    .modal-footer {
        border: 0;
        padding: 0;
    }
}
</style>
